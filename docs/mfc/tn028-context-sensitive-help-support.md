---
title: "TN028&#160;: prise en charge de l&#39;aide contextuelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.help"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aide contextuelle, applications MFC"
  - "identificateurs de ressources, aide contextuelle"
  - "TN028"
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN028&#160;: prise en charge de l&#39;aide contextuelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les règles pour affecter des ID d'aide de contexte et d'autres problèmes d'aide de MFC.  La prise en charge d'aide contextuelle requiert le compilateur d'aide qui est disponible dans Visual C\+\+.  
  
> [!NOTE]
>  En plus d'implémenter l'aide contextuelle à l'aide de WinHelp, MFC fait également de la prise en charge en utilisant l'aide HTML.  Pour plus d'informations sur la prise en charge et la programmation à l'aide d'HTML, consultez l' [Aide HTML : Aide contextuelle pour les programmes](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## Types d'aide pris en charge  
 Il existe deux types d'aide contextuelle implémentés dans les applications Windows.  Le premier, également connu sous le nom de « touche F1 » implique de lancer le WinHelp avec le contexte approprié basé sur l'objet actuellement actif.  Le deuxième mode est le mode « Shift\+ F1 ».  Dans ce mode, le curseur de la souris se change en curseur d'aide, et l'utilisateur se charge de cliquer sur un objet.  À ce stade, WinHelp est exécuté pour apporter l'aide de l'objet sur lequel l'utilisateur a cliqué.  
  
 L'outil Microsoft Foundation Classes implémente ces deux formes d'aide.  En outre, l'infrastructure prend en charge deux commandes d'aide simples, l'index d'aide et l'aide d'utilisation.  
  
## Fichiers d'aide  
 Les classes Microsoft Foundation sous\-entendent un seul fichier d'aide.  Ce fichier d'aide doit avoir le même nom et le même chemin d'accès que l'application.  Par exemple, si le fichier exécutable est C:\\MyApplication\\MyHelp.exe le fichier d'aide doit être C:\\MyApplication\\MyHelp.hlp.  Vous définissez le chemin d'accès à travers l'attribut `m_pszHelpFilePath` de [CWinApp Class](../mfc/reference/cwinapp-class.md).  
  
## Chaînes de contexte d'aide  
 L'implémentation par défaut de MFC requiert un programme pour suivre des règles sur l'attribution des ID de contexte d'aide.  Ces règles sont une plage d'ID alloués aux contrôles spécifiques.  Vous pouvez remplacer ces règles en fournissant des implémentations des fonctions membres liées à l'aide.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
   0x00010000 + ID_  
   (note: 0x18000-> 0x1FFFF is the practical range since command IDs are >=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
   0x00020000 + IDR_  
   (note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
   0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
   0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
   0x00040000 + IDW_  
```  
  
## Commandes « Aide » simples  
 Il existe deux commandes d'aide implémentées par Microsoft Foundation Classes :  
  
-   ID\_HELP\_INDEX qui est implémenté par [CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)  
  
-   ID\_HELP\_USING implémenté par [CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)  
  
 La première commande montre l'index d'aide pour l'application.  Le second montre l'aide utilisateur sur l'utilisation du programme WinHelp.  
  
## Aide contextuelle \(Aide F1\)  
 La touche F1 est généralement traduite en une commande avec un ID d' `ID_HELP` par un accélérateur placé dans la table de la fenêtre principale des accélérateurs.  L'ordre d' `ID_HELP` peut également être générée par un bouton à un ID d' `ID_HELP` de la fenêtre principale ou de la boîte de dialogue.  
  
 Quelle que soit la façon dont la commande d' `ID_HELP` est créée, elle est acheminée en tant que commande standard jusqu'à ce qu'elle atteigne un gestionnaire de commandes.  Pour plus d'informations sur l'architecture de routage des commandes de MFC, reportez\-vous à la [Note technique 21](../mfc/tn021-command-and-message-routing.md).  Si l'application a son l'aide activée, la commande `ID_HELP` sera gérée par [CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md).  L'objet d'application reçoit le message d'aide puis achemine la commande correctement.  Cela est nécessaire car le routage des commandes par défaut n'est pas adéquat pour déterminer le contexte le plus spécifique.  
  
 `CWinApp::OnHelp` tente de lancer WinHelp dans l'ordre suivant :  
  
1.  Recherche un appel actif d' `AfxMessageBox` à l'aide d'un ID d'aide  Si une boîte de message est actuellement active, WinHelp s'exécute avec le contexte adapté à ce message.  
  
2.  Envoie un message de WM\_COMMANDHELP à la fenêtre active.  Si cette fenêtre ne répond pas en lançant WinHelp, le même message est ensuite envoyé aux ancêtres de cette fenêtre jusqu'à ce que le message soit traité ou que la fenêtre active soit une fenêtre de niveau supérieur.  
  
3.  Envoie une commande de ID\_DEFAULT\_HELP à la fenêtre principale.  Ce code appelle l'aide par défaut.  Cette commande est généralement mappée à `CWinApp::OnHelpIndex`.  
  
 Pour remplacer globalement les valeurs par défaut de la base d'identification \(par exemple 0x10000 pour les commandes et 0x20000 des ressources telles que les dialogues\), l'application doit remplacer [CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md).  
  
 Pour remplacer cette fonctionnalité et la façon dont le contexte d'aide est déterminé, vous devez traiter le message de WM\_COMMANDHELP.  Vous pouvez fournir plus de routage d'aide spécifique que l'infrastructure fournit, car il ne descend qu'aussi profond que les fenêtres enfants MDI active.  Vous pouvez aussi fournir davantage d'aide spécifique pour une fenêtre ou une conversation particulière, éventuellement en fonction de l'état interne actuel de cet objet ou le contrôle actif dans la boîte de dialogue.  
  
## WM\_COMMANDHELP  
  
```  
  
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
```  
  
 WM\_COMMANDHELP est un message privé Windows MFC qui est reçu par la fenêtre active lorsque l'aide est demandée.  Lorsque la fenêtre reçoit le message, elle peut appeler `CWinApp::WinHelp` avec le contexte qui correspond à l'état interne de la fenêtre.  
  
 `lParam`  
 Contient le contexte d'aide actuellement disponible.  `lParam` est nul si aucun contexte d'aide n'a été déterminé.  Une implémentation de `OnCommandHelp` peut utiliser l'ID de contexte de `lParam` pour déterminer un contexte différent ou simplement le passer à `CWinApp::WinHelp`.  
  
 `wParam`  
 N'est pas utilisé et sera égal à zéro.  
  
 Si la fonction `OnCommandHelp` appelle `CWinApp::WinHelp`, il retourne `TRUE`.  Retourner `TRUE` arrête le routage de cette commande vers d'autres classes et d'autres fenêtres.  
  
## Mode d'aide \(aide Shift\+F1\)  
 Ceci est le format d'aide contextuelle.  En général, ce mode est entré en appuyant sur SHIFT\+F1 ou via le menu\/la barre d'outils.  Il est implémenté en tant que commande \(**ID\_CONTEXT\_HELP**\).  Le raccordement de message n'est pas utilisé pour convertir cette commande lorsqu'une boîte de dialogue modale ou un menu est actif, c'est pourquoi cette commande est uniquement disponible pour l'utilisateur lorsque l'application exécute la pompe des messages principaux \(`CWinApp::Run`\).  
  
 Après avoir entré ce mode, le curseur de la souris d'aide s'affiche sur tous les domaines d'application, même si l'application afficherait normalement son propre curseur pour cette zone \(telles que la bordure de dimensionnement autour de la fenêtre\).  L'utilisateur peut utiliser la souris ou le clavier pour sélectionner une commande.  Au lieu d'exécuter la commande, l'aide de cette commande s'affiche.  En outre, l'utilisateur peut cliquer sur un objet visible dans l'écran, tel qu'un bouton dans la barre d'outils, puis l'aide pour cet objet s'affiche.  Ce mode d'utilisation est fourni par `CWinApp::OnContextHelp`.  
  
 Pendant l'exécution de cette boucle, toutes les entrées du clavier sont inactives, à l'exception des clés qui accèdent au menu.  En outre, la traduction de commande est toujours effectuée via `PreTranslateMessage` pour permettre à l'utilisateur d'appuyez sur une touche d'accès rapide et de recevoir l'aide de cette commande.  
  
 S'il existe des traductions spécifiques ou des actions ayant lieu dans la fonction `PreTranslateMessage` qui ne devraient pas avoir lieu en mode d'aide SHIFT\+F1, vous devez vérifier l'attribut `m_bHelpMode` d'`CWinApp` avant d'effectuer ces opérations.  L'implémentation de `CDialog` d'`PreTranslateMessage` vérifie cela avant d'appeler `IsDialogMessage`, par exemple.  Cela désactive les touches de « navigation de dialogue » dans les boîtes de dialogue non modales en mode SHIFT\+F1.  En outre, `CWinApp::OnIdle` est tout de même appelé pendant cette boucle.  
  
 Si l'utilisateur choisit une commande dans le menu, il est géré comme aide de la commande \(par **WM\_COMMANDHELP**, voir ci\-dessous\).  Si l'utilisateur clique sur une zone visible de la fenêtre d'applications, une détermination est effectuée pour savoir s'il s'agit d'un clic non client ou d'un clic client.  Mappage automatique de descripteurs d' `OnContextHelp` de clics non clients vers des clics clients.  S'il s'agit d'un clic client, il envoie ensuite **WM\_HELPHITTEST** à la fenêtre sur laquelle on a cliqué.  Si cette fenêtre retourne une valeur différente de zéro, cette valeur est utilisée comme contexte d'aide.  S'il retourne la valeur zéro, `OnContextHelp` essaye la fenêtre parente \(et si cela échoue, son parent, etc.\).  Si un contexte d'aide ne peut pas être déterminée, le comportement par défaut est d'envoyer une commande d' **ID\_DEFAULT\_HELP** à la fenêtre principale, qui ensuite \(généralement\) est mappée à `CWinApp::OnHelpIndex`.  
  
## WM\_HELPHITTEST  
  
```  
  
afx_msg LRESULT CWnd::OnHelpHitTest(  
WPARAM, LPARAM lParam)  
```  
  
 **WM\_HELPHITTEST** est une fenêtre de message privé MFC qui est reçue par la fenêtre active sur lequel on a cliqué en mode d'aide SHIFT\+F1.  Lorsque la fenêtre reçoit le message, elle renvoie l'ID d'aide DWORD destinée à WinHelp.  
  
 LOWORD \(lParam\)  
 contient la coordonnée de périphérique de l'axe des abscisses dans laquelle la souris a cliqué par rapport à la zone client de la fenêtre.  
  
 HIWORD \(lParam\)  
 Contient la coordonnée de l'axe Y.  
  
 `wParam`  
 n'est pas utilisé et sera égal à zéro.  Si la valeur de retour est différente de zéro, WinHelp est appelé avec ce contexte.  Si la valeur de retour est zéro, la fenêtre parente est interrogée pour obtenir de l'aide.  
  
 Dans de nombreux cas, vous pouvez tirer parti du code que vous avec peut\-être déjà pour faire du test de positionnement.  Consultez l'implémentation de **CToolBar::OnHelpHitTest** pour obtenir un exemple de façon de gérer le message de **WM\_HELPHITTEST** \(le code profite du code de test de positionnement utilisé sur des boutons et des info\-bulles dans `CControlBar`\).  
  
## Prise en charge de l'Assistant d'Application et MAKEHM MFC  
 L'Assistant d'Application MFC crée les fichiers nécessaires pour générer un fichier d'aide \(fichiers de .cnt et de .hpj\).  Il inclut également plusieurs fichiers prégénérés de .rtf reçus par le compilateur d'aide Microsoft.  Plusieurs rubriques sont complètes, mais certaines doivent être modifiées pour votre application spécifique.  
  
 La création automatique d'un fichier « mappage d'aide » est prise en charge par l'utilitaire appelé MAKEHM.  L'utilitaire de MAKEHM peut traduire le fichier de RESOURCE.H d'une application vers un fichier de mappage d'aide.  Par exemple :  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 est convertie en :  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Ce format est compatible avec la fonctionnalité d'aide du compilateur, qui mappe les ID de contexte \(les nombres à droite\) avec les noms d'élément \(les symboles du côté gauche\).  
  
 Le code source pour MAKEHM est disponible dans l'exemple d'utilitaire de programmation MFC [MAKEHM](../top/visual-cpp-samples.md).  
  
## Permet d'ajouter une prise en charge après l'exécution de l'Assistant d'Application MFC  
 La meilleure méthode pour ajouter de l'aide à votre application consiste à activer l'option « aide contextuelle » sur la page de fonctionnalités avancées de l'Application MFC avant de créer votre application.  De cette façon l'Application MFC ajoute automatiquement les entrées de la table des messages nécessaires à votre classe dérivée de `CWinApp` pour prendre en charge l'aide.  
  
## Aide sur les boîtes de messages  
 L'aide sur les messages \(parfois appelés des alertes\) est prise en charge par la fonction d' `AfxMessageBox`, un wrapper pour l'API Windows pour `MessageBox`.  
  
 Il existe deux versions de `AfxMessageBox`, un pour une utilisation avec un ID de chaîne et un autre pour une utilisation avec un pointeur de chaîne \(`LPCSTR`\) :  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText, UINT nType, UINT nIDHelp);  
int AFXAPI AfxMessageBox(UINT nIDPrompt, UINT nType, UINT nIDHelp);  
```  
  
 Dans les deux cas, il y a un ID facultative d'aide  
  
 Dans le premier cas, la valeur par défaut pour le nIDHelp est 0, qui n'indique aucune aide de ce message.  Si l'utilisateur appuye sur F1 lorsque le message est actif, l'utilisateur n'accepte pas d'aide \(même si l'application prend en charge l'aide\).  Si ce n'est pas souhaitable, un ID d'aide doit être fourni pour le nIDHelp.  
  
 Dans le deuxième cas, la valeur par défaut pour le nIDHelp est \-1, ce qui indique que l'ID d'aide est identique au nIDPrompt.  L'aide fonctionne uniquement si l'aide de l'application est activée, naturellement\).  Vous devez fournir 0 pour le nIDHelp si vous souhaitez que le message n'ait aucune aide.  Si vous souhaitez que le message ait son aide activée, mais désirez un autre ID d'aide que le nIDPrompt, entrez simplement une valeur positive du nIDHelp différente de celle du nIDPrompt.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)