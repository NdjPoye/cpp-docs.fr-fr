---
title: "AFX, messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SB_LINELEFT"
  - "SB_THUMBTRACK"
  - "AFX_TOOLTIP_TYPE_EDIT"
  - "AFX_WM_ON_HSCROLL"
  - "SB_PAGERIGHT"
  - "AFX_WM_RESETPROMPT"
  - "AFX_WM_CHANGE_RIBBON_CATEGORY"
  - "AFX_TOOLTIP_TYPE_MINIFRAME"
  - "AFX_WM_CUSTOMIZETOOLBAR"
  - "AFX_WM_CHANGE_ACTIVE_TAB"
  - "AFX_WM_ACCGETOBJECT"
  - "AFX_WM_TOOLBARMENU"
  - "AFX_TOOLTIP_TYPE_DOCKBAR"
  - "AFX_WM_CUSTOMIZEHELP"
  - "AFX_WM_ON_GET_TAB_TOOLTIP"
  - "AFX_WM_ON_RIBBON_CUSTOMIZE"
  - "AFX_WM_ON_DRAGCOMPLETE"
  - "AFX_WM_RESETTOOLBAR"
  - "AFX_WM_ON_MOVETOTABGROUP"
  - "AFX_WM_CHECKEMPTYMINIFRAME"
  - "AFX_WM_GETDOCUMENTCOLORS"
  - "SB_RIGHT"
  - "AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU"
  - "AFX_WM_ACCGETSTATE"
  - "SB_PAGELEFT"
  - "SB_ENDSCROLL"
  - "AFX_WM_ON_CANCELTABMOVE"
  - "AFX_TOOLTIP_TYPE_TAB"
  - "AFX_WM_WINDOW_HELP"
  - "AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM"
  - "AFX_WM_SHOWREGULARMENU"
  - "AFX_TOOLTIP_TYPE_TOOLBAR"
  - "AFX_WM_CHANGE_CURRENT_FOLDER"
  - "AFX_WM_UPDATETOOLTIPS"
  - "AFX_WM_ON_MOVE_TAB"
  - "AFX_WM_CHANGING_ACTIVE_TAB"
  - "AFX_WM_RESETMENU"
  - "AFX_WM_GETDRAGBOUNDS"
  - "AFX_WM_RESETCONTEXTMENU"
  - "AFX_TOOLTIP_TYPE_BUTTON"
  - "AFX_WM_ON_CLOSEPOPUPWINDOW"
  - "AFX_TOOLTIP_TYPE_TOOLBOX"
  - "AFX_WM_CHANGEVISUALMANAGER"
  - "SB_LINERIGHT"
  - "AFX_WM_ON_RENAME_TAB"
  - "AFX_TOOLTIP_TYPE_DEFAULT"
  - "AFX_WM_ON_TABGROUPMOUSEMOVE"
  - "SB_LEFT"
  - "AFX_WM_DELETETOOLBAR"
  - "AFX_WM_PROPERTY_CHANGED"
  - "AFX_TOOLTIP_TYPE_ALL"
  - "AFX_WM_ACCHITTEST"
  - "AFX_WM_ON_AFTER_SHELL_COMMAND"
  - "AFX_WM_ON_PRESS_CLOSE_BUTTON"
  - "AFX_WM_RESETKEYBOARD"
  - "AFX_WM_ON_MOVETABCOMPLETE"
  - "AFX_WM_CREATETOOLBAR"
  - "SB_THUMBPOSITION"
  - "AFX_WM_POSTSETPREVIEWFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX (messages)"
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# AFX, messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces messages sont utilisés dans MFC.  
  
## Messages  
 Le tableau suivant répertorie les messages utilisés dans la bibliothèque MFC :  
  
||||||  
|-|-|-|-|-|  
|Message|Description|\[in\] `wParam`|`lParam` \(tous les paramètres sont \[in\] sauf indication contraire.\)|Valeur de retour|  
|AFX\_WM\_ACCGETOBJECT|Non utilisé.|Non utilisé.|Non applicable.|Non applicable.|  
|AFX\_WM\_ACCGETSTATE|Utilisé pour la prise en charge de l'accessibilité.  Envoyez ce message à `CMFCPopupMenu` ou à `CMFCRibbonPanelMenu` pour récupérer l'état de l'élément actuel.|Indice de l'élément, qui peut être un bouton de menu ou un séparateur.|Non utilisé.|L'état de l'élément.  La valeur est \-1 si l'indice n'est pas valide, 0 si le bouton de menu n'a pas d'attribut spécial.  Sinon il s'agit d'une combinaison des indicateurs suivants :<br /><br /> TBBS\_DISABLED – le service est désactivé<br /><br /> TBBS\_CHECKED – l'élément est activé<br /><br /> TBBS\_BUTTON – l'élément est un bouton poussoir standard<br /><br /> TBBS\_PRESSED – le bouton est pressé<br /><br /> TBBS\_INDETERMINATE – état indéfini<br /><br /> TBBS\_SEPARATOR \- plutôt qu'un bouton de menu, cet élément forme une séparation entre d'autres éléments de menu|  
|AFX\_WM\_CHANGE\_ACTIVE\_TAB|L'infrastructure envoie ce message dans le contrôle redimensionnable de la barre de contrôle.  Traitez ce message pour recevoir des notifications d'objets `CMFCTabCtrl` lorsqu'un utilisateur modifie un onglet actif.|L'indice d'un onglet.|Non utilisé.|Une valeur différente de zéro.|  
|AFX\_WM\_CHANGE\_CURRENT\_FOLDER|L'infrastructure envoie le message au parent de `CMFCShellListCtrl` lorsque l'utilisateur a modifié le dossier actif.|Non utilisé.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_CHANGEVISUALMANAGER|L'infrastructure envoie ce message à toutes les fenêtres cadres lorsque l'utilisateur modifie le gestionnaire visuel actuel.  En réponse à ce message, une fenêtre cadre recalcule la zone et ajuste les autres paramètres si nécessaire.  Vous pouvez traiter le message AFX\_WM\_CHANGEVISUALMANAGER dans votre application si vous devez être informé sur cet événement.  Vous devez appeler le gestionnaire de classe de base \(`OnChangeVisualManager`\) pour garantir que le traitement interne de l'infrastructure de cet événement a lieu.|Non utilisé.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_CHANGING\_ACTIVE\_TAB|Envoyé au parent de l'objet `CMFCTabCtrl`.  Traitez ce message si vous souhaitez recevoir des notifications d'objets `CMFCTabCtrl` lorsqu'un utilisateur réinitialise un onglet.|Indice de l'onglet activé.|Non utilisé.|Une valeur différente de zéro.|  
|AFX\_WM\_CHECKEMPTYMINIFRAME|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.|Non applicable.|  
|AFX\_WM\_CREATETOOLBAR|Envoyé de `CMFCToolBarsListPropertyPage` lorsqu'un utilisateur crée une barre d'outils lors du processus de personnalisation.  Vous pouvez traiter ce message pour instancier un objet personnalisé dérivé de CMFCToolBar.  Si vous traitez ce message et créez votre propre barre d'outils, omettez l'appel au gestionnaire par défaut.|Non utilisé.|Pointeur vers une chaîne qui contient le nom de la barre d'outils.|Pointeur vers la barre d'outils nouvellement créée.  NULL indique que la création de la barre d'outils a été annulée.|  
|AFX\_WM\_CUSTOMIZEHELP|Envoyé à la fenêtre principale cadre de la feuille de propriétés de personnalisation `CMFCToolbarCustomize``Dialog` lorsque l'utilisateur appuie sur le bouton **Aide** ou la touche F1.|Spécifie la page active de la feuille de propriétés de personnalisation.|Un pointeur vers un objet `CMFCToolbarCustomize``Dialog`.|Zéro.|  
|AFX\_WM\_CUSTOMIZETOOLBAR|Le `CMFCToolbarCustomize``Dialog` envoie ce message pour notifier le cadre parent que l'utilisateur crée une barre d'outils.|`TRUE` lorsque la personnalisation est démarrée, `FALSE` lorsque la personnalisation est terminée.|Non utilisé.|Zéro.|  
|AFX\_WM\_DELETETOOLBAR|Envoyé à la fenêtre principale cadre lorsque l'utilisateur est sur le point de supprimer une barre d'outils dans le mode de personnalisation.<br /><br /> Traitez ce message pour entreprendre des actions supplémentaires lorsque l'utilisateur supprime une barre d'outils dans le mode de personnalisation.  Vous devez appeler le gestionnaire par défaut \(`OnToolbarDelete`\), ce qui supprime la barre d'outils.  Le gestionnaire par défaut retourne une valeur qui indique s'il est possible de supprimer la barre d'outils.|Non utilisé.|Pointeur vers un objet `CMFCToolBar` à supprimer.|Une valeur différente de zéro si une barre d'outils ne peut pas être supprimée ; sinon 0.|  
|AFX\_WM\_GETDOCUMENTCOLORS|`CMFCColorMenuButton` envoie ce message à la fenêtre principale cadre pour récupérer les couleurs de document.|Non utilisé.|\[in, out\] Pointeur vers un objet `CList<COLORREF, COLORREF>`.|Zéro.|  
|AFX\_WM\_GETDRAGBOUNDS|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.|Non applicable.|  
|AFX\_WM\_HIGHLIGHT\_RIBBON\_LIST\_ITEM|Envoyé à la fenêtre principale cadre lorsqu'un utilisateur met en surbrillance un élément de la liste de ruban.|Indice de l'élément surligné.|Un pointeur vers `CMFCBaseRibbonElement`.|Non utilisé.|  
|AFX\_WM\_ON\_AFTER\_SHELL\_COMMAND|Envoyé à un parent des contrôles `CMFCShellListCtrl` ou `CMFCShellTreeCtrl` lorsqu'un utilisateur a fini d'exécuter une commande d'environnement.|ID de la commande que l'utilisateur a exécutée|Non utilisé.|Si l'application traite les messages, elle devrait retourner zéro.|  
|AFX\_WM\_ON\_BEFORE\_SHOW\_RIBBON\_ITEM\_MENU|L'infrastructure envoie ce message vers le parent du ruban pour qu'il affiche le menu contextuel.  Vous pouvez traiter ce message et modifier les menus contextuels à tout moment.|Non utilisé.|Un pointeur vers `CMFCBaseRibbonElement`.|Non utilisé.|  
|AFX\_WM\_ON\_CANCELTABMOVE|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.||  
|AFX\_WM\_ON\_CHANGE\_RIBBON\_CATEGORY|L'infrastructure envoie ce message dans le cadre principal lorsque l'utilisateur modifie la catégorie active de contrôle du ruban.|Non utilisé.|Un pointeur vers le `CMFCRibbonBar` dont la catégorie a changé.|Non utilisé.|  
|AFX\_WM\_ON\_CLOSEPOPUPWINDOW|L'infrastructure envoie ce message pour notifier le propriétaire de `CMFCDesktopAlertWnd` que la fenêtre va être fermée.|Non utilisé.|Un pointeur vers un objet `CMFCDesktopAlertWnd`.|Non utilisé.|  
|AFX\_WM\_ON\_DRAGCOMPLETE|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.|Non applicable.|  
|AFX\_WM\_ON\_GET\_TAB\_TOOLTIP|Envoyé à la fenêtre principale cadre lorsqu'une fenêtre d'onglet est sur le point d'afficher une info\-bulle de l'onglet, si les info\-bulles personnalisées sont activées.|Non utilisé.|Pointeur vers une structure `CMFCTabToolTipInfo`.|Non utilisé.|  
|AFX\_WM\_ON\_HSCROLL|Envoyé au contrôle redimensionnable de la barre de contrôle.  Traitez ce message pour recevoir des notifications d'objets `CMFCTabCtrl` lorsqu'un événement de défilement apparaît dans la barre de défilement horizontale de widget à onglets.|Le mot d'ordre réduit spécifie une valeur de barre de défilement qui indique la demande de défilement de l'utilisateur.  Pour plus d'informations, consultez la table plus loin dans cette rubrique.|Non utilisé.|Une valeur différente de zéro.|  
|AFX\_WM\_ON\_MOVE\_TAB|Envoyé au parent d'une fenêtre avec onglets lorsqu'un utilisateur fait glisser un onglet vers une nouvelle position.|Indice de base zéro de l'onglet dans son emplacement d'origine.|\[out\] Indice de base zéro de l'onglet dans son nouvel emplacement.|Zéro.|  
|AFX\_WM\_ON\_MOVETABCOMPLETE|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.|Non applicable.|  
|AFX\_WM\_ON\_MOVETOTABGROUP|Envoyé à la fenêtre principale cadre lorsqu'un utilisateur déplace une fenêtre enfant MDI d'un groupe tabulé à un autre.|Un handle à la fenêtre avec onglets \(`CMFCTabCtrl`\) de laquelle la fenêtre enfant MDI a été supprimée.|\[out\] handle de la fenêtre avec onglets\(`CMFCTabCtrl`\) à laquelle la fenêtre enfant MDI a été insérée.|Ignoré.|  
|AFX\_WM\_ON\_PRESS\_CLOSE\_BUTTON|Envoyé à un parent de `CDockablePane` lorsque l'utilisateur clique sur le bouton **Fermer** sur la légende de la barre de contrôle.|Non utilisé.|Pointeur vers un volet ancrable dans lequel l'utilisateur a cliqué sur le bouton **Fermer**.|`TRUE` si le volet ne peut pas être fermé ; FALSE sinon.|  
|AFX\_WM\_ON\_RENAME\_TAB|Envoyé au parent de la fenêtre avec onglets après que l'utilisateur ait renommé un onglet modifiable.|Indice de base zéro de l'onglet renommé.|\[out\] Pointeur vers la chaîne qui contient le nouveau nom d'onglet.|Une valeur différente de zéro si l'application traite ce message ; l'infrastructure supprimera l'appel à `CMFCBaseTabCtrl::SetTabLabel`.  Si NULL est retourné, alors `CMFCBaseTabCtrl::SetTabLabel` est appelé par l'infrastructure.|  
|AFX\_WM\_ON\_RIBBON\_CUSTOMIZE|Envoyé au cadre parent lorsque l'utilisateur lance la personnalisation.  Traitez ce message si vous souhaitez afficher votre propre boîte de dialogue de personnalisation.|Non utilisé.|Pointeur vers le contrôle de ruban à personnaliser.|Une valeur différente de zéro si l'application traite ce message et affiche sa propre boîte de dialogue de personnalisation.  Si l'application retourne zéro, l'infrastructure affiche la boîte de dialogue intégrée de personnalisation.|  
|AFX\_WM\_ON\_TABGROUPMOUSEMOVE|Uniquement réservé à un usage interne.|Non applicable.|Non applicable.|Non applicable.|  
|AFX\_WM\_POSTSETPREVIEWFRAME|Envoyé pour notifier le cadre principal que l'utilisateur a modifié le mode aperçu avant impression|`TRUE` indique que le mode aperçu avant impression est défini.  `FALSE` indique que le mode aperçu avant impression est désactivé.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_PROPERTY\_CHANGED|Envoyé au propriétaire du contrôle de la grille des propriétés \(`CMFCPropertyGridCtrl`\)lorsque l'utilisateur modifie la valeur de la propriété sélectionnée.|L'ID du contrôle de la liste de propriétés|Pointeur vers la propriété \(`CMFCProp``ertyGridProperty`\) qui a changé.|Non utilisé.|  
|AFX\_WM\_RESETCONTEXTMENU|Envoyé à la fenêtre principale cadre lorsque l'utilisateur réinitialise le menu contextuel de la personnalisation.|Numéro de l'ID du menu de contexte.|Un pointeur au menu de contexte actuel, `CMFCPopupMenu`.|Non utilisé.|  
|AFX\_WM\_RESETKEYBOARD|L'infrastructure envoie ce message à la fenêtre principale cadre lorsque l'utilisateur réinitialise toutes les touches d'accès rapides pendant la personnalisation.|Non utilisé.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_RESETMENU|L'infrastructure envoie le message au propriétaire du menu \(une fenêtre cadre\) lorsque l'utilisateur réinitialise un menu du cadre d'application pendant la personnalisation|L'ID de ressource menu.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_RESETPROMPT|L'infrastructure envoie ce message lorsque l'utilisateur réinitialise une barre d'outils de la boîte de dialogue de personnalisation.  Le gestionnaire par défaut affiche un message qui vous demande si l'utilisateur souhaite réinitialiser la barre d'outils.|Non utilisé.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_RESETTOOLBAR|Un objet `CMFCToolBar` envoie ce message lorsqu'une barre d'outils est restaurée à son état initial, ie chargée à partir des ressources.  Traitez ce message pour réinsérer les boutons de la barre d'outils dont les classes sont dérivées de `CMFCToolbarButton`.  Pour plus d'informations, consultez `CMFCToolbarComboBoxButton`.|L'ID de ressource d'une barre d'outils dont l'état a été restauré.|Non utilisé.|Zéro.|  
|AFX\_WM\_SHOWREGULARMENU|L'objet `CMFCToolbarMenuButton` envoie ce message à son propriétaire lorsque l'utilisateur clique sur un bouton de menu standard.  Traitez ce message à chaque fois que vous utilisez `CMFCToolbarMenuButton` pour afficher un menu contextuel lorsque l'utilisateur clique sur un bouton.|ID de commande d'un bouton qui envoie le message.|Coordonnées d'écran du curseur.  Le mot d'ordre réduit spécifie la coordonnée x.  Le mot de poids fort spécifie la coordonnée y.|Non utilisé.|  
|AFX\_WM\_TOOLBARMENU|Envoyé à la fenêtre principale cadre lorsque l'utilisateur libère le bouton droit de la souris pendant que le pointeur de la souris est dans la zone cliente ou non cliente d'un volet.|Non utilisé.|Coordonnées écran du pointeur de la souris.  Le mot d'ordre réduit spécifie la coordonnée x.  Le mot de poids fort spécifie la coordonnée y.|Zéro si l'application traite ce message ; sinon, la valeur est différente de zéro.|  
|AFX\_WM\_UPDATETOOLTIPS|Diffusé à tous les propriétaires d'info\-bulle pour indiquer que les contrôles d'info\-bulle doivent être recréés.|Le type de contrôle qui doit traiter ce message.  Consultez le tableau plus loin dans cette rubrique pour obtenir la liste des valeurs possibles.|Non utilisé.|Non utilisé.|  
|AFX\_WM\_WINDOW\_HELP|`CMFCWindowsManagerDialog` envoie ce message dans le cadre parent lorsque l'utilisateur clique sur le bouton **Aide**, ou entre le mode d'aide en cliquant sur le bouton de légende **Aide** ou la touche F1.|Non utilisé.|Pointeur vers l'instance de `CMFCWindowsManagerDialog`.|Non utilisé.|  
  
 Le tableau suivant indique les valeurs pour le bas mot du paramètre `lParam` de la méthode d'AFX\_WM\_HSCROLL :  
  
|||  
|-|-|  
|Valeur|Signification|  
|SB\_ENDSCROLL|L'utilisateur termine le défilement.|  
|SB\_LEFT|L'utilisateur défile dans la direction supérieure gauche.|  
|SB\_RIGHT|L'utilisateur défile dans la direction bas droite.|  
|SB\_LINELEFT|L'utilisateur fait défiler à gauche d'une unité.|  
|SB\_LINERIGHT|L'utilisateur fait défiler à droite d'une unité.|  
|SB\_PAGELEFT|L'utilisateur fait défiler à gauche de la largeur de la fenêtre.|  
|SB\_PAGERIGHT|L'utilisateur fait défiler à droite de la largeur de la fenêtre.|  
|SB\_THUMBPOSITION|L'utilisateur a déplacé la case de défilement \(curseur de défilement\) et laché le bouton de la souris.  Le mot de poids fort indique la position de la case de défilement à la fin de l'opération glisser\-déplacer.|  
|SB\_THUMBTRACK|L'utilisateur fait glisser la case de défilement.  Le message AFX\_WM\_ON\_HSCROLL est envoyé à plusieurs reprises avec cette valeur jusqu'à ce que l'utilisateur lache le bouton de la souris.  Le mot de poids fort indique la position à laquelle la case de défilement a été déplacée.|  
  
> [!NOTE]
>  Le mot de poids fort du paramètre `lParam` spécifie la position actuelle de la case de défilement si le mot de poids faible est SB\_THUMBPOSITION ou SB\_THUMBTRACK ; sinon, le mot n'est pas utilisé.  
  
 Le tableau suivant répertorie les valeurs d'indicateur pour le paramètre `lParam` du message AFX\_WM\_UPDATETOOLTIPS :  
  
|||  
|-|-|  
|Indicateur|Valeur|  
|AFX\_TOOLTIP\_TYPE\_DEFAULT|0x0001|  
|AFX\_TOOLTIP\_TYPE\_TOOLBAR|0x0002|  
|AFX\_TOOLTIP\_TYPE\_TAB|0x0004|  
|AFX\_TOOLTIP\_TYPE\_MINIFRAME|0x0008|  
|AFX\_TOOLTIP\_TYPE\_DOCKBAR|0x0010|  
|AFX\_TOOLTIP\_TYPE\_EDIT|0x0020|  
|AFX\_TOOLTIP\_TYPE\_BUTTON|0x0040|  
|AFX\_TOOLTIP\_TYPE\_TOOLBOX|0x0080|  
|AFX\_TOOLTIP\_TYPE\_ALL|0xFFFF|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)