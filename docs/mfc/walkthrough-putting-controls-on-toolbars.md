---
title: "Proc&#233;dure pas &#224; pas&#160;: placement de contr&#244;les dans les barres d&#39;outils | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Boîte de dialogue Personnaliser, ajouter des contrôles"
  - "barres d'outils, ajouter des contrôles"
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
caps.latest.revision: 24
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: placement de contr&#244;les dans les barres d&#39;outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment ajouter un bouton de barre d'outils qui contient un contrôle Windows.  Dans MFC, un bouton de barre d'outils doit être une classe dérivée de [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md), par exemple [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), ou [CMFCToolBarMenuButton Class](../mfc/reference/cmfctoolbarmenubutton-class.md).  
  
## Ajout de contrôles à la barre d'outils  
 Pour ajouter un contrôle à une barre d'outils, suivez ces étapes :  
  
1.  Réservez un ID de ressource fictive pour le bouton dans la ressource de la barre d'outils parente.  Pour plus d'informations sur la création de boutons à l'aide de l'Éditeur de barres d'outils dans Visual Studio, consultez la rubrique [Toolbar Editor](../mfc/toolbar-editor.md).  
  
2.  Réservez une image de barre d'outils \(icône du bouton\) pour le bouton dans toutes les bitmaps de la barre d'outils parente.  
  
3.  Dans le gestionnaire de messages qui gère le message `AFX_WM_RESETTOOLBAR`, procédez comme suit :  
  
    1.  Construisez le contrôle bouton à l'aide d'une classe dérivée de `CMFCToolbarButton`.  
  
    2.  Remplacez le bouton fictif par le nouveau contrôle en utilisant [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  Vous pouvez construire l'objet bouton sur la pile, car `ReplaceButton` copie l'objet bouton et maintient la copie.  
  
> [!NOTE]
>  Si vous activez la personnalisation dans votre application, vous aurez peut\-être à redéfinir la barre d'outils en utilisant le bouton **Réinitialiser** sur l'onglet **Barres d'outils** de la boîte de dialogue **Personnaliser** pour afficher le contrôle mis à jour dans votre application après recompilation.  L'état de la barre d'outils est stocké dans le Registre Windows, et les informations de Registre sont chargées et appliquées après que la méthode `ReplaceButton` est exécutée pendant le démarrage de l'application.  
  
## Contrôles de barre d'outils et personnalisation  
 L'onglet **Commandes** de la boîte de dialogue **Personnaliser** contient une liste des commandes disponibles dans l'application.  Par défaut, la boîte de dialogue **Personnaliser** exécute les menus d'application et construit une liste de boutons de barre d'outils standard dans chaque catégorie de menu.  Pour conserver la fonctionnalité étendue que les contrôles de barre d'outils fournissent, vous devez remplacer le bouton de barre d'outils standard par le contrôle personnalisé dans la boîte de dialogue **Personnaliser**.  
  
 Lorsque vous activez la personnalisation, vous créez la boîte de dialogue **Personnaliser** dans le gestionnaire `OnViewCustomize` de personnalisation en utilisant la classe [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md).  Avant d'afficher la boîte de dialogue **Personnaliser** en appelant [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md), appelez [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) pour remplacer le bouton standard par le nouveau contrôle.  
  
## Exemple : Création d'une zone de liste déroulante de recherche  
 Cette section décrit comment créer un contrôle de liste déroulante `Find` qui apparaît dans une barre d'outils et contient les chaînes utilisées récemment.  L'utilisateur peut entrer une chaîne du contrôle puis appuyez sur la touche d'entrée pour rechercher un document, ou appuyez sur la touche ESCAPE pour retourner le focus au frame principal.  Cet exemple suppose que le document est affiché dans [CEditView Class](../mfc/reference/ceditview-class.md)\- Affichage dérivée.  
  
### Création du contrôle de recherche  
 En premier lieu, créez le contrôle de la zone de liste modifiable `Find` :  
  
1.  Ajoutez le bouton et ses commandes aux ressources d'application :  
  
    1.  Dans les ressources d'application, ajoutez un nouveau bouton avec un ID de commande `ID_EDIT_FIND` à une barre d'outils de votre application et à toutes les bitmap associées à la barre d'outils.  
  
    2.  Créez un élément de menu avec l'ID de commande des ID\_EDIT\_FIND  
  
    3.  Ajoutez une nouvelle chaîne « recherchez le texte\\nFind » à la table de chaînes et assignez\-lui un ID de commande `ID_EDIT_FIND_COMBO` Cet ID sera utilisé comme ID de commande du bouton de zone de liste déroulante `Find`.  
  
        > [!NOTE]
        >  Comme `ID_EDIT_FIND` est une commande standard traitée par `CEditView`, vous n'êtes pas tenus d'implémenter un gestionnaire spécial pour cette commande.  Toutefois, vous devez implémenter un gestionnaire pour la nouvelle commande `ID_EDIT_FIND_COMBO`.  
  
2.  Créez une nouvelle classe, `CFindComboBox`, dérivée de [CComboBox Class](../mfc/reference/ccombobox-class.md).  
  
3.  Dans la classe `CFindComboBox`, substituez la méthode virtuelle `PreTranslateMessage`.  Cette méthode permet à la zone de liste déroulante de traiter le message [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280).  Si l'utilisateur appuie la touche Echap \(`VK_ESCAPE`\), retournez le focus sur la fenêtre frame principale.  Si l'utilisateur appuie la touche Entrée \(`VK_ENTER`\), publiez à la fenêtre frame principale un message `WM_COMMAND` contenant l'ID de commande `ID_EDIT_FIND_COMBO`  
  
4.  Créez une classe pour le bouton de zone de liste déroulante `Find`, dérivée de [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  Dans cet exemple, cela est nommé `CFindComboButton`.  
  
5.  Le constructeur de `CMFCToolbarComboBoxButton` prend trois paramètres : l'ID de commande du bouton, l'index d'images de bouton, et le style de la zone de liste déroulante.  Définissez ces paramètres comme suit :  
  
    1.  Passez `ID_EDIT_FIND_COMBO` comme ID de commande  
  
    2.  Utilisez [CCommandManager::GetCmdImage](http://msdn.microsoft.com/fr-fr/4094d08e-de74-4398-a483-76d27a742dca) avec `ID_EDIT_FIND` pour obtenir l'index de l'image.  
  
    3.  Pour une liste des styles disponibles de la liste déroulante, consultez [Styles de zone de liste modifiable](../mfc/reference/combo-box-styles.md).  
  
6.  Dans la classe `CFindComboButton`, remplacez la méthode `CMFCToolbarComboBoxButton::CreateCombo`.  Maintenant vous devez créer l'objet `CFindComboButton` et retourner un pointeur vers lui.  
  
7.  Utilisez la macro [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) pour rendre le bouton modifiable persistant.  Le gestionnaire de l'espace de travail charge et stocke automatiquement l'état du bouton dans le Registre Windows.  
  
8.  Implémentez le gestionnaire `ID_EDIT_FIND_COMBO` dans l'affichage de document.  Utilisez [CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md) avec `ID_EDIT_FIND_COMBO` pour récupérer tous les boutons de zone de liste déroulante `Find`.  Il peut exister plusieurs copies d'un bouton avec le même ID de commande suite à la personnalisation.  
  
9. Dans le gestionnaire de messages `OnFind`d'ID\_EDIT\_FIND, utilisez [CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md) pour déterminer si la commande Find a été envoyée du bouton de zone de liste déroulante `Find`.  Si oui, recherchez le texte et ajoutez la chaîne recherchée dans la zone de liste déroulante.  
  
### Ajout du contrôle de recherche dans la barre d'outils principale  
 Pour ajouter le bouton de zone de liste déroulante à la barre d'outils, suivez ces étapes :  
  
1.  Implémentez le gestionnaire de messages `OnToolbarReset` de `AFX_WM_RESETTOOLBAR` dans la fenêtre frame principale.  
  
    > [!NOTE]
    >  L'infrastructure envoie le message à la fenêtre frame principale lorsqu'une barre d'outils est initialisée pendant le démarrage de l'application, ou lorsqu'une barre d'outils est réinitialisée pendant la personnalisation.  Dans les deux cas, vous devez remplacer le bouton de barre d'outils standard par le bouton de zone de liste déroulante `Find` personnalisé.  
  
2.  Dans le gestionnaire `AFX_WM_RESETTOOLBAR`, examinez l'ID de barre d'outils, autrement. Autrement dit, `WPARAM` du message `AFX_WM_RESETTOOLBAR`.  Si l'ID de barre d'outils est égal à celui de la barre d'outils qui contient le bouton de zone de liste déroulante `Find`, appelez [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) pour remplacer le bouton `Find` \(autrement dit, celui dont l'ID de commande `ID_EDIT_FIND)` avec un objet `CFindComboButton`.  
  
    > [!NOTE]
    >  Vous pouvez construire un objet `CFindComboBox` sur la pile, ceci car `ReplaceButton` copie le bouton et maintient la copie.  
  
### Ajout du contrôle de correspondance dans la boîte de dialogue Personnaliser  
 Dans le gestionnaire `OnViewCustomize`de personnalisation, appelez [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md) pour remplacer le bouton `Find` \(autrement dit, celui dont l'ID de commande `ID_EDIT_FIND)` avec un objet `CFindComboButton`.  
  
## Voir aussi  
 [Graphique hiérarchique](../mfc/hierarchy-chart.md)   
 [Classes](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md)