---
title: "TN028 : Prise en charge de l’aide contextuelle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.help
dev_langs: C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8054fe4fae4aafa88c34833a5a2a92a6b9b44bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tn028-context-sensitive-help-support"></a>TN028 : prise en charge de l'aide contextuelle
Cette note décrit les règles permettant d'affecter des ID d'aide contextuelle et d'autres problèmes liés à l'aide dans MFC. La prise en charge de l'aide contextuelle requiert le compilateur d'aide qui est disponible dans Visual C++.  
  
> [!NOTE]
>  En plus d'implémenter l'aide contextuelle avec WinHelp, MFC offre également un support en utilisant l'aide HTML. Pour plus d’informations sur cette prise en charge et la programmation avec HTML (aide), consultez [aide HTML : aide contextuelle pour vos programmes](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## <a name="types-of-help-supported"></a>Types d'aide pris en charge  
 Il existe deux types d'aide contextuelle implémentés dans les applications Windows. Le premier, également connu sous le nom de "F1 Aide" implique de lancer WinHelp avec le contexte approprié basé sur l'objet actuellement actif. Le deuxième type est le mode "Maj+ F1". Dans ce mode, le curseur de la souris se change en curseur d'aide, et l'utilisateur se charge de cliquer sur un objet. À ce stade, WinHelp est exécuté pour apporter l'aide de l'objet sur lequel l'utilisateur a cliqué.  
  
 L'outil Microsoft Foundation Classes implémente ces deux formes d'aide. En outre, le framework prend en charge deux commandes d'aide simples, l'index d'aide et l'utilisation de l'aide.  
  
## <a name="help-files"></a>Fichiers d’aide  
 Les classes Microsoft Foundation sous-entendent un seul fichier d'aide. Ce fichier d'aide doit avoir le même nom et le même chemin d'accès que l'application. Par exemple, si le fichier exécutable est C:\MyApplication\MyHelp.exe, le fichier d'aide sera C:\MyApplication\MyHelp.hlp. Vous définissez le chemin d’accès via le `m_pszHelpFilePath` variable membre de la [CWinApp (classe)](../mfc/reference/cwinapp-class.md).  
  
## <a name="help-context-ranges"></a>Plages contextuelles d'aide  
 L'implémentation par défaut de MFC requiert un programme pour suivre des règles sur l'attribution des ID de contexte d'aide. Ces règles sont une plage d'ID alloués à des contrôles spécifiques. Vous pouvez remplacer ces règles en fournissant des implémentations des fonctions membres liées à l'aide.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
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
  
## <a name="simple-help-commands"></a>Commandes "Aide" simples  
 Il existe deux commandes d'aide implémentées par Microsoft Foundation Classes :  
  
-   ID_HELP_INDEX qui est implémentée par [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   ID_HELP_USING qui est implémentée par [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 La première commande montre l'index d'aide pour l'application. La seconde montre l'aide utilisateur sur l'utilisation du programme WinHelp.  
  
## <a name="context-sensitive-help-f1-help"></a>Aide contextuelle (F1 Aide)  
 La touche F1 est généralement traduite en une commande avec un ID `ID_HELP` par un accélérateur placé dans la table d'accélérateurs de la fenêtre principale. La commande `ID_HELP` peut également être générée par un bouton avec un ID `ID_HELP` de la fenêtre principale ou de la boîte de dialogue.  
  
 Quelle que soit la façon dont la commande `ID_HELP` est créée, elle est acheminée en tant que commande standard jusqu'à ce qu'elle atteigne un gestionnaire de commandes. Pour plus d’informations sur l’architecture de routage des commandes MFC, consultez [Note technique 21](../mfc/tn021-command-and-message-routing.md). Si l’application a aide activé, le `ID_HELP` commande sera gérée par [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). L'objet d'application reçoit le message d'aide puis achemine la commande correctement. Cela est nécessaire car le routage des commandes par défaut n'est pas adéquat pour déterminer le contexte le plus spécifique.  
  
 `CWinApp::OnHelp` tente de lancer WinHelp dans l'ordre suivant :  
  
1.  Recherche un appel `AfxMessageBox` actif à l'aide d'un ID d'aide Si une boîte de message est actuellement active, WinHelp s'exécute avec le contexte adapté à ce message.  
  
2.  Envoie un message WM_COMMANDHELP à la fenêtre active. Si cette fenêtre ne répond pas en lançant WinHelp, le même message est ensuite envoyé aux ancêtres de cette fenêtre jusqu'à ce que le message soit traité ou que la fenêtre active soit une fenêtre de niveau supérieur.  
  
3.  Envoie une commande ID_DEFAULT_HELP à la fenêtre principale. Ce code appelle l'aide par défaut. Cette commande est généralement mappée à `CWinApp::OnHelpIndex`.  
  
 Pour remplacer des globalement les valeurs de code base par défaut (par exemple, 0 x 10000 pour les commandes et 0 x 20000 pour des ressources telles que les boîtes de dialogue), l’application doit substituer [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp).  
  
 Pour remplacer cette fonctionnalité et la façon dont le contexte d'aide est déterminé, vous devez traiter le message WM_COMMANDHELP. Vous pouvez fournir davantage de routage d'aide spécifique que fournit par le framework, car il peut accéder aux niveaux de fenêtres enfants MDI actives les plus bas. Vous pouvez également fournir davantage d'aide spécifique pour une fenêtre ou une boîte de dialogue particulière, éventuellement en fonction de l'état interne actuel de cet objet ou le contrôle actif dans la boîte de dialogue.  
  
## <a name="wmcommandhelp"></a>WM_COMMANDHELP  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 WM_COMMANDHELP est un message Windows MFC privé qui est reçu par la fenêtre active lorsque l'Aide est demandée. Lorsque la fenêtre reçoit le message, elle peut appeler `CWinApp::WinHelp` avec le contexte qui correspond à l'état interne de la fenêtre.  
  
 `lParam`  
 Contient le contexte d'aide actuellement disponible. `lParam` est nul si aucun contexte d'aide n'a été déterminé. Une implémentation de `OnCommandHelp` peut utiliser l'ID de contexte de `lParam` pour déterminer un contexte différent ou simplement le passer à `CWinApp::WinHelp`.  
  
 `wParam`  
 N'est pas utilisé et sera égal à zéro.  
  
 Si la fonction `OnCommandHelp` appelle `CWinApp::WinHelp`, elle retourne `TRUE`. Retourner `TRUE` arrête le routage de cette commande vers d'autres classes et d'autres fenêtres.  
  
## <a name="help-mode-shiftf1-help"></a>Mode d'aide (Maj+F1 Aide)  
 Il s'agit de la seconde forme d'aide contextuelle. En général, ce mode est accessible en appuyant sur Maj+F1 ou via le menu/la barre d'outils. Il est implémenté en tant que commande (**ID_CONTEXT_HELP**). Le raccordement de filtre de messages ne permet pas de convertir cette commande lorsqu'une boîte de dialogue ou un menu modal est actif, c'est pourquoi cette commande est uniquement disponible pour l'utilisateur lorsque l'application exécute la pompe de message principal (`CWinApp::Run`).  
  
 Après avoir accédé à ce mode, le curseur de souris de l'Aide s'affiche sur toutes les zones de l'application, même si elle affiche normalement son propre curseur pour cette zone (telles que la bordure de dimensionnement autour de la fenêtre). L'utilisateur peut utiliser la souris ou le clavier pour sélectionner une commande. Au lieu d'exécuter la commande, l'aide de cette commande s'affiche. En outre, l'utilisateur peut cliquer sur un objet visible à l'écran, tel qu'un bouton dans la barre d'outils, puis l'Aide de cet objet s'affiche. Ce mode d'utilisation est fourni par `CWinApp::OnContextHelp`.  
  
 Pendant l'exécution de cette boucle, toutes les entrées du clavier sont inactives, à l'exception des touches qui accèdent au menu. En outre, la conversion des commandes est toujours effectuée via `PreTranslateMessage` pour permettre à l'utilisateur d'appuyer sur une touche d'accès rapide et de recevoir l'aide de cette commande.  
  
 Si des conversions ou des actions spécifiques se produisent dans la fonction `PreTranslateMessage` qui ne devraient pas avoir lieu en mode d'aide Maj+F1, vous devriez vérifier le membre `m_bHelpMode` de `CWinApp` avant d'effectuer ces opérations. L'implémentation de `CDialog` pour `PreTranslateMessage` vérifie cela avant d'appeler `IsDialogMessage`, par exemple. Cela désactive les touches de "navigation dans les boîtes de dialogue" pour les boîtes de dialogue non modales en mode Maj+F1. En outre, `CWinApp::OnIdle` est tout de même appelé pendant cette boucle.  
  
 Si l’utilisateur choisit une commande dans le menu, elle est gérée en tant qu’aide sur la commande (via **WM_COMMANDHELP**, voir ci-dessous). Si l'utilisateur clique sur une zone visible de la fenêtre d'applications, il est déterminé s'il s'agit d'un clic non client ou d'un clic client. `OnContextHelp` gère le mappage des clics non clients aux clics clients. S’il s’agit d’un clic client, il envoie ensuite un **WM_HELPHITTEST** dans la fenêtre de l’utilisateur a cliqué. Si cette fenêtre retourne une valeur différente de zéro, cette valeur est utilisée comme contexte d'aide. Si elle retourne la valeur zéro, `OnContextHelp` essaie la fenêtre parente (et en cas d'échec, ainsi de suite). Si un contexte d’aide ne peut pas être déterminé, la valeur par défaut est d’envoyer un **ID_DEFAULT_HELP** commande à la fenêtre principale, qui (est ensuite en général) mappée à `CWinApp::OnHelpIndex`.  
  
## <a name="wmhelphittest"></a>WM_HELPHITTEST  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 **WM_HELPHITTEST** est un message windows privé MFC qui est reçu par un clic lors du mode d’aide MAJ + F1 dans la fenêtre active. Lorsque la fenêtre reçoit le message, elle renvoie l'ID d'aide DWORD destinée à WinHelp.  
  
 LOWORD (lParam)  
 contient la coordonnée de périphérique de l'axe X où la souris a été cliquée par rapport à la zone cliente de la fenêtre.  
  
 HIWORD (lParam)  
 contient la coordonnée de l'axe Y.  
  
 `wParam`  
 n'est pas utilisé et sera égal à zéro. Si la valeur de retour est différente de zéro, WinHelp est appelé avec ce contexte. Si la valeur de retour est zéro, la fenêtre parente est interrogée pour obtenir de l'aide.  
  
 Dans de nombreux cas, vous pouvez tirer parti du code que vous avez peut-être déjà pour effectuer un test de positionnement. Consultez l’implémentation de **CToolBar::OnHelpHitTest** pour obtenir un exemple de la gestion du **WM_HELPHITTEST** message (le code s’appuie sur le code de test de positionnement utilisé sur des boutons et des info-bulles dans `CControlBar`).  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>Prise en charge de l'Assistant Application MFC et MAKEHM  
 L'Assistant Application MFC crée les fichiers nécessaires pour générer un fichier d'aide (fichiers .cnt et .hpj). Il inclut également plusieurs fichiers .rtf prégénérés qui sont acceptés par le compilateur d'aide Microsoft. Plusieurs rubriques sont complètes, mais certaines doivent être modifiées pour votre application spécifique.  
  
 La création automatique d'un fichier de "mappage d'aide" est prise en charge par l'utilitaire appelé MAKEHM. L'utilitaire MAKEHM peut convertir le fichier RESOURCE.H d'une application en un fichier de mappage d'aide. Exemple :  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 est converti en :  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Ce format est compatible avec la fonctionnalité d'aide du compilateur, qui mappe les ID de contexte (les nombres à droite) aux noms d'élément (les symboles à gauche).  
  
 Le code source de MAKEHM est disponible dans l’exemple utilitaires de programmation MFC [MAKEHM](../visual-cpp-samples.md).  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>Ajout de la prise en charge de l'Aide après exécution de l'Assistant Application MFC  
 La meilleure méthode pour ajouter de l'aide à votre application consiste à activer l'option "Aide contextuelle"sur la page des fonctionnalités avancées de l'Assistant Application MFC avant de créer votre application. De cette façon, l'Assistant Application MFC ajoute automatiquement les entrées de la table des messages nécessaires à votre classe dérivée de `CWinApp` pour prendre en charge l'Aide.  
  
## <a name="help-on-message-boxes"></a>Aide sur les boîtes de message  
 L'Aide sur les boîtes de messages (parfois appelées alertes) est prise en charge par la fonction `AfxMessageBox`, un wrapper pour l'API Windows `MessageBox`.  
  
 Il existe deux versions de `AfxMessageBox`, un pour une utilisation avec un ID de chaîne et une autre pour une utilisation avec un pointeur de chaîne (`LPCSTR`) :  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 Dans les deux cas, il y a un ID d'aide facultatif.  
  
 Dans le premier cas, la valeur par défaut de nIDHelp est 0, qui n'indique aucune aide pour cette boîte de message. Si l'utilisateur appuie sur la touche F1 lorsque le message est actif, il n'acceptera pas d'aide (même si l'application prend en charge l'aide). Si ce n'est pas souhaitable, un ID d'aide doit être fourni pour nIDHelp.  
  
 Dans le deuxième cas, la valeur par défaut de nIDHelp est -1, ce qui indique que l'ID d'aide est identique à nIDPrompt. Bien évidemment, l'Aide fonctionne uniquement si la fonction d'aide de l'application est activée. Vous devez fournir 0 pour nIDHelp si vous souhaitez que la boîte de message ne propose aucune aide. Si vous souhaitez que l'aide du message soit activée, mais avec un autre ID d'aide que nIDPrompt, entrez simplement une valeur positive pour nIDHelp différente de celle de nIDPrompt.  
  
## <a name="see-also"></a>Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
