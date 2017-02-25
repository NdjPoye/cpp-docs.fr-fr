---
title: "TN021&#160;: Routage des commandes et des messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.routing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routage des commandes (C++), note technique TN021"
  - "TN021"
  - "messages Windows (C++), router"
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# TN021&#160;: Routage des commandes et des messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette note décrit le routage des commandes et la l'architecture de livraison ainsi que des sujet traitant du routage de messages de fenêtre en général.  
  
 Rendez\-vous sur Visual C\+\+ pour obtenir des informations générales sur les architectures décrites ici, notamment la distinction entre les messages Windows, les notifications de contrôle et les commandes.  Cette remarque suppose que vous êtes très familier avec les problèmes décrits dans la documentation et ne traite que de sujets très avancés.  
  
## La fonctionnalité de MFC 1,0 de routage de commandes et de livraisons évolue en l'architecture de MFC 2,0  
 Windows a le message de **WM\_COMMAND** qui est surchargé pour afficher les notifications des commandes de menu, des touches d'accès rapide et les notifications de contrôle de la boîte de dialogue.  
  
 MFC 1,0 s'est un peu basé dessus en permettant à un gestionnaire de commandes \(par exemple, « OnFileNew »\) dans une classe dérivée **CWnd** d'obtenir appelé en réponse à **WM\_COMMAND**spécifique.  Cela est collé ensemble avec une structure de données appelée table de messages, et résulte en un mécanisme de commande très efficace en termes d'espace.  
  
 MFC . fournissait également des fonctionnalités supplémentaires permettant de séparer les notifications de contrôles des messages de commande.  Les commandes sont représentées par un ID 16 bits, parfois appelée un ID de commande  Normalement les commandes démarrent à partir de **CFrameWnd** \(autrement dit, un menu ou un accès rapide translaté\) et se font acheminer vers diverses autres fenêtres.  
  
 MFC . utilisait le routage de commande dans un sens assez limité pour l'implémentation de l'interface de documents multiples \(MDI\). \(Un délégué fenêtre de cadre MDI commande à sa fenêtre enfant MDI active.\)  
  
 Cette fonctionnalité a été généralisée et étendue dans MFC 2,0 pour autoriser des commandes devant être gérées par un éventail d'objets plus important \(pas seulement les objets fenêtres\).  Il fournit une architecture plus formelle et plus évolutive pour le routage des messages et réutilise le routage de cible de commande pour gérer non seulement les commandes, mais aussi pour mettre à jour les objets de l'interface utilisateur\(IU\) \(tels que les éléments de menu et les boutons de la barre d'outils\) pour indiquer la disponibilité actuelle d'une commande.  
  
## ID de commande  
 Consultez Visual C\+\+ pour une explication du routage des commandes et du processus de liaison.  [Note technique 20](../mfc/tn020-id-naming-and-numbering-conventions.md) contient des informations sur les noms d'identification.  
  
 Nous utilisons le terme préfixe générique « ID\_ » pour les ID de commande.  Les ID de commande sont \>\= 0x8000.  La ligne ou la barre d'état du message affiche la chaîne de description de commande s'il existe une ressource STRINGTABLE avec les mêmes ID que l'ID de commande.  
  
 Dans les ressources de votre application, une boîte d'ID de commande apparaît dans plusieurs endroits :  
  
-   Dans une ressource STRINGTABLE portant le même ID que l'invite de ligne du message.  
  
-   Dans probablement plusieurs ressources MENU qui sont jointes aux éléments de menu qui invoquent la même commande.  
  
-   \(AVANCÉ\) dans un bouton de dialogue d'une commande de GOSUB.  
  
 Dans le code source de votre application, une boîte d'ID de commande peut apparaître dans plusieurs endroits :  
  
-   Dans votre RESOURCE.H \(ou un autre fichier de symbole d'en\-tête principal\) pour définir des ID de commande spécifiques à l'application.  
  
-   PEUT\-ÊTRE dans un tableau d'ID utilisé pour créer une barre d'outils.  
  
-   Dans une macro **ON\_COMMAND**.  
  
-   PEUT\-ÊTRE dans une macro **ON\_UPDATE\_COMMAND\_UI**.  
  
 Actuellement, la seule implémentation de MFC qui requiert que les ID de commande soient \>\= 0x8000 est l'implémentation des dialogues\/commandes de GOSUB.  
  
## Commandes de GOSUB, selon l'architecture de commande dans les dialogues  
 L'architecture de commande de routage et d'activation des commandes marches bien avec les fenêtres cadres, les éléments de menu, les boutons de barres d'outils, les boutons de barres de dialogues, les autres barres de contrôle et les autres éléments d'interface créés pour mettre à jour sur demande et aiguiller les commandes ou les IDs de contrôle vers une cible de commande principale \(habituellement la fenêtre cadre principale\).  Cette cible de commande peut aiguiller les notifications de commande ou de contrôle vers d'autres objets de la cible de la commande selon ce qui est approprié.  
  
 Un dialogue \(modal ou non modal\) peut tirer parti des fonctionnalités de l'architecture de commande si vous affectez l'ID de contrôle du contrôle de la boîte de dialogue à l'ID de commande appropriée.  La prise en charge des conversations n'est pas automatique, vous devrez peut\-être écrire du code supplémentaire.  
  
 Notez que pour que toutes ces fonctionnalités fonctionnent correctement, les ID de la commande doivent être \>\= 0x8000.  Étant donné que de nombreux dialogues peuvent se faire aiguiller vers le même cadre, les commandes partagées doivent être \>\= 0x8000, tandis que les IDC non partagées dans une conversation spécifique doivent être \<\= 0x7FFF.  
  
 Vous pouvez placer un bouton classique dans une boîte de dialogue modale normale en assignant à l'IDC du bouton l'ID de commande appropriée.  Lorsque l'utilisateur sélectionne le bouton, le propriétaire de la boîte de dialogue \(généralement la fenêtre principale\) obtient la commande comme toute autre commande.  Cela s'appelle une commande de GOSUB, car elle est généralement utilisée pour effectuer un autre dialogue \(un GOSUB du premier dialogue\).  
  
 Vous pouvez également appeler la fonction **CWnd::UpdateDialogControls** sur votre dialogue et lui transmettre l'adresse de votre fenêtre principale.  Cette fonction activera ou désactivera les contrôles de la boîte de dialogue selon qu'elles contiennent des gestionnaires de commandes dans le cadre ou pas.  Cette fonction est appelée automatiquement pour vous pour les barres de contrôles dans la boucle inactive de votre application, mais vous devez l'appeler directement pour les dialogues standards que vous voulez voir posséder cette option.  
  
## Lorsqu'est appelé ON\_UPDATE\_COMMAND\_UI  
 Maintenir l'état activé\/coché de tous les éléments de menu d'un programme tout le temps peut être un problème gourmand en ressources informatiques.  Une technique commune est d'activer\/cocher les éléments de menus uniquement quand l'utilisateur sélectionne le POPUP.  L'implémentation dans MFC 2,0 de **CFrameWnd** traite le message de **WM\_INITMENUPOPUP** et utilise l'architecture de routage des commandes pour déterminer les états des menus à travers les gestionnaires de **ON\_UPDATE\_COMMAND\_UI**.  
  
 **CFrameWnd** traite également le message de **WM\_ENTERIDLE** pour décrire l'élément de menu qui est sélectionné dans la barre d'état \(également appelée ligne de message\).  
  
 La structure du menu d'une application, modifiée par Visual C\+\+, est utilisée pour représenter les commandes potentielles disponibles au moment de **WM\_INITMENUPOPUP**.  Les gestionnaires de **ON\_UPDATE\_COMMAND\_UI** peuvent modifier l'état ou le texte d'un élément, ou dans le cas des utilisations avancés \(comme la liste des fichiers récents ou le menu contextuel d'actions verbales OLE\), modifier réellement la structure du menu avant que le menu soit affiché.  
  
 Le même genre de traitement de **ON\_UPDATE\_COMMAND\_UI** est effectué pour les barres d'outils \(et d'autres barres de contrôle\) lorsque l'application entre dans sa boucle inactive.  Consultez *la bibliothèque de classes de référence* et la [Note technique 31](../mfc/tn031-control-bars.md) pour plus d'informations sur les barres de contrôle.  
  
## Menus contextuels imbriqués  
 Si vous utilisez une structure imbriquée de menu, vous remarquerez que le gestionnaire de **ON\_UPDATE\_COMMAND\_UI** du premier élément de menu dans le menu contextuel est appelée dans deux cas distincts.  
  
 En premier lieu, il est appelée pour le menu contextuel lui\-même.  Cela est nécessaire car les menus contextuels n'ont aucun ID et nous utilisons l'ID du premier élément de menu dans le menu contextuel pour faire référence au menu contextuel entier.  Dans ce cas, la variable membre de **m\_pSubMenu** de l'objet de **CCmdUI** ne sera pas NULL et indiquera le menu contextuel.  
  
 Ensuite, il est appelé immédiatement avant que les éléments du menu dans le menu contextuel doivent être affichés.  Dans ce cas, l'ID se rapporte uniquement au premier élément de menu et la variable membre de **m\_pSubMenu** de l'objet de **CCmdUI** sera NULL.  
  
 Cela vous permet d'activer le menu contextuel distinctement de ses éléments de menu, mais il suppose que vous écriviez du code de conscience de menu.  Par exemple, dans un menu imbriqué ayant la structure suivante :  
  
```  
File>  
    New>  
        Sheet (ID_NEW_SHEET)  
        Chart (ID_NEW_CHART)  
```  
  
 Les commandes d'ID\_NEW\_SHEET et d'ID\_NEW\_CHART peuvent être activées ou désactivées indépendamment.  Le **Nouveau** menu contextuel doit être activé si l'un des deux est activé.  
  
 Le gestionnaire de commandes pour ID\_NEW\_SHEET \(la première commande dans le popup\) est présenté quelque chose comme :  
  
```  
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)  
{  
    if (pCmdUI->m_pSubMenu != NULL)  
    {  
        // enable entire pop-up for "New" sheet and chart  
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;  
  
        // CCmdUI::Enable is a no-op for this case, so we  
        //   must do what it would have done.  
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,  
            MF_BYPOSITION |   
                (bEnable ? MF_ENABLED : (MF_DISABLED | MF_GRAYED)));  
        return;  
    }  
    // otherwise just the New Sheet command  
    pCmdUI->Enable(m_bCanCreateSheet);  
}  
```  
  
 Le gestionnaire de commandes pour ID\_NEW\_CHART est un gestionnaire de commandes standard et ressemble un peu à ça :  
  
```  
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)  
{  
    pCmdUI->Enable(m_bCanCreateChart);  
}  
```  
  
## ON\_COMMAND et ON\_BN\_CLICKED  
 Les macros de table des messages pour **ON\_COMMAND** et **ON\_BN\_CLICKED** sont les mêmes.  Le mécanisme de routage de notification de commande et de contrôle de MFC utilise uniquement l'ID de commande pour déterminer vers où aiguiller.  Les notifications de contrôle avec un code de notification de contrôle à zero \(**BN\_CLICKED**\) sont interprétées comme des commandes.  
  
> [!NOTE]
>  En fait, tous les messages de notification passent par la chaîne du gestionnaire de commandes.  Par exemple, il est possible techniquement d'écrire un gestionnaire de notification de contrôle pour **EN\_CHANGE** dans la classe du document.  Ce n'est généralement pas recommandée car les applications pratiques de cette fonctionnalité sont peu nombreuses, la fonctionnalité n'est pas prise en charge par ClassWizard, et l'utilisation de la fonctionnalité peut entraîner une fragilité du code.  
  
## Désactiver la désactivation automatique des contrôles bouton.  
 Si vous placez un contrôle bouton dans la barre de la boîte de dialogue, ou dans une boîte de dialogue dans laquelle vous appelez **CWnd::UpdateDialogControls** sur les vôtres, vous remarquerez que les boutons qui n'ont pas de gestionnaires de **ON\_COMMAND** ou de **ON\_UPDATE\_COMMAND\_UI** sont automatiquement désactivés pour vous par l'infrastructure.  Dans certains cas, vous n'avez pas besoin d'avoir un gestionnaire, mais vous souhaitez que le bouton reste actif.  La façon la plus simple d'y parvenir consiste à ajouter un gestionnaire de commandes factice \(facile à réaliser avec ClassWizard\) et ne rien faire avec.  
  
## Routage des messages de la fenêtre  
 La section suivante décrit encore des rubriques avancées sur les classes de MFC et comment le routage des messages windows et d'autres rubriques les affectent.  L'information ici est décrite très brièvement  Consultez *la référence de la bibliothèque de classes* pour plus d'informations sur les API publique.  Référez vous au code source de la bibliothèque MFC pour plus d'informations sur les détails d'implémentation.  
  
 Rendez\-vous sur la [Note technique 17](../mfc/tn017-destroying-window-objects.md) pour plus d'informations sur le nettoyage de la fenêtre, une rubrique très important pour les classes dérivées **CWnd**.  
  
## Problèmes de CWnd  
 La fonction membre **CWnd::OnChildNotify** d'implémentation fournit une architecture extensible puissante pour que les fenêtres enfants \(également appelées contrôles\) se raccordent ou autrement être informé des messages, commandes, et notifications de contrôle qui mènent à son parent \(ou « propriétaire »\).  Si la fenêtre enfant \(\/contrôle\) est un objet de **CWnd** de C\+\+ elle\-même, la fonction virtuelle **OnChildNotify** est appelée en premier avec les paramètres du message original \(autrement dit, une structure de **MSG** \).  La fenêtre enfant peut laisser le message tranquille, le manger, ou modifier le message pour le parent \(rare\).  
  
 L'implémentation de **CWnd** par défaut traite les messages suivants et utilise le raccordement de **OnChildNotify** pour permettre aux fenêtres enfants \(contrôles\) le premier accès au message :  
  
-   **WM\_MEASUREITEM** et **WM\_DRAWITEM** \(pour le dessin automatique\)  
  
-   **WM\_COMPAREITEM** et **WM\_DELETEITEM** \(pour le dessin automatique\)  
  
-   **WM\_HSCROLL** et **WM\_VSCROLL**  
  
-   **WM\_CTLCOLOR**  
  
-   **WM\_PARENTNOTIFY**  
  
 Vous remarquerez le raccordement de **OnChildNotify** est utilisé pour transforemr les messages de dessin de propriétaire en des messages de dessin automatique.  
  
 En plus du raccordement par **OnChildNotify**, les messages de défilement ont un comportement de routage qui va plus loin.  Veuilez regarder ci\-dessous pour plus de détails sur les barres de défilement et les sources de messages **WM\_HSCROLL** et **WM\_VSCROLL**.  
  
## Problèmes de CFrameWnd  
 La classe **CFrameWnd** fournit la majorité du routage des commandes et de l'implémentation de la mise à jour de l'interface utilisateur.  Ceci est principalement utilisé pour la fenêtre principale de l'application \(**CWinApp::m\_pMainWnd**\) mais s'applique à toutes les fenêtres cadres.  
  
 La fenêtre principale est la fenêtre qui a la barre de menus et qui est le parent de la barre d'état ou de la ligne du message.  Rendez\-vous sur une description ci\-dessus sur le routage des commandes et **WM\_INITMENUPOPUP.**  
  
 La classe de **CFrameWnd** permet de gérer la vue active.  Les messages suivants sont routés via la vue active :  
  
-   Tous les messages de commande \(la vue active obtient le premier accès\).  
  
-   Messages de**WM\_HSCROLL** et de **WM\_VSCROLL** venant des barres de défilement soeurs \(voir ci\-dessous\).  
  
-   **WM\_ACTIVATE** \(et **WM\_MDIACTIVATE** pour MDI\) se font transformer en appels à la fonction virtuelle **CView::OnActivateView**.  
  
## Problèmes de CMDIFrameWnd\/CMDIChildWnd  
 Les deux classes de fenêtre cadre MDI dérivent de **CFrameWnd** et sont donc toutes deux activées pour le même genre de routage de commande et de mise à jour de l'interface utilisateur fournis par **CFrameWnd**.  Dans une application classique MDI, seule la fenêtre principale \(autrement dit, l'objet de **CMDIFrameWnd** \) contient la barre de menus et la barre d'état et par conséquent est la principale source d'implémentation de routage des commandes.  
  
 Le schéma général de routage est que la fenêtre enfant MDI active obtient le premier accès aux commandes.  Les fonctions de **PreTranslateMessage** par défaut gère les tables d'accès rapides pour les fenêtres enfants MDI \(d'abord\) et le cadre MDI \(ensuite\) ainsi que les accès\-rapides standard des systèmes commande MDI généralement gérés par **TranslateMDISysAccel** \(en dernier\).  
  
## Problèmes de barre de défilement  
 Quand vous gérez le message à défilement \(**WM\_HSCROLL**\/**OnHScroll** et\/ou **WM\_VSCROLL**\/**OnVScroll**\), vous devez essayer d'écrire le code du gestionnaire afin qu'il ne compte pas sur l'endroit d'où le message de barre de défilement a été obtenu.  Il s'agit pas uniquement d'un problème général de Windows, comme les messages de défilement peuvent provenir de véritables contrôles de la barre de défilement, ou de barres de défilement de **WS\_HSCROLL**\/**WS\_VSCROLL** qui ne sont pas des contrôles de barre de défilement.  
  
 MFC étend ça pour permettre que les contrôles de la barre de défilement soient des enfants ou des frères de la fenêtre où le défilement s'effectue \(en fait, la relation parent\/enfant entre la barre de défilement et la fenêtre où le défilement se fait peut être n'importe laquelle\).  Cela est particulièrement important pour les barres de défilement partagées avec des fenêtres à fractionnement.  Rendez\-vous sur la [Note technique 29](../mfc/tn029-splitter-windows.md) pour plus d'informations sur l'implémentation de **CSplitterWnd**, incluant plus d'informations sur les problèmes de barres de défilement partagées.  
  
 Sur une note marginale, il existe deux classes dérivées de **CWnd** où les styles de barre de défilement spécifiés lors de la création sont interceptés et non transmis à Windows.  Une fois transmis à une routine de conception, **WS\_HSCROLL** et **WS\_VSCROLL** peuvent être définies indépendamment, mais après la création ne peuvent pas être modifiés.  Naturellement, vous ne devez pas directement tester ou définir les bits du WS\_?SCROLL de la fenêtre qu'ils ont créées.  
  
 Pour **CMDIFrameWnd** les styles de barre de défilement que vous passez à **Créer** ou **LoadFrame** sont utilisés pour créer le MDICLIENT.  Si vous voulez posséder une liste déroulante de MDICLIENT \(tels que le gestionnaire de programmes Windows\) veillez à définir les deux styles de barre de défilement \(**WS\_HSCROLL** &#124; **WS\_VSCROLL**\) pour le style utilisé pour créer **CMDIFrameWnd**.  
  
 Pour **CSplitterWnd** les styles de barre de défilement s'appliquent aux barres de défilement partagées spéciales pour les régions de séparation.  Pour les fenêtres de fractionnement statiques, vous ne devez affecter normalement ni l'un ni l'autre de ces styles.  Pour les fenêtres de fractionnement dynamiques, vous aurez généralement le style de la barre de défilement défini pour le sens que vous fractionnerez, c'est\-à\-dire, **WS\_HSCROLL** si vous pouvez fractionner des lignes, **WS\_VSCROLL** si vous pouvez fractionner des colonnes.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)