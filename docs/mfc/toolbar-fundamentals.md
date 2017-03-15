---
title: "Notions de base de barre d&#39;outils | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RT_TOOLBAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants Application (C++), installer des barres d'outils d'application par défaut"
  - "ID de commande, boutons de barre d'outils"
  - "CToolBar (classe), barres d'outils par défaut dans l'Assistant Application"
  - "incorporer une barre d'outils dans la classe de fenêtre frame"
  - "classes de fenêtre frame, barre d'outils incorporée dans"
  - "LoadBitmap (méthode), barres d'outils"
  - "LoadToolBar (méthode)"
  - "ressources (MFC), barre d'outils"
  - "RT_TOOLBAR (ressource)"
  - "SetButtons (méthode)"
  - "contrôles de barre d'outils (MFC), ID de commande"
  - "contrôles de barre d'outils (MFC), barres d'outils créées à l'aide de l'Assistant Application"
  - "Éditeur de barres d'outils, Assistant Application"
  - "barres d'outils (C++), ajouter par défaut à l'aide de l'Assistant Application"
  - "barres d'outils (C++), créer"
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Notions de base de barre d&#39;outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique l'implémentation MFC fondamentale qui vous permet d'ajouter une barre d'outils par défaut à votre application en sélectionnant une option dans l'Assistant d'Application.  Les rubriques traitées ici sont les suivantes :  
  
-   [L'option barre d'outil de l'Assistant d'Application.](#_core_the_appwizard_toolbar_option)  
  
-   [La barre d'outils dans le code](#_core_the_toolbar_in_code)  
  
-   [Modifier la ressource barre d'outils](#_core_editing_the_toolbar_resource)  
  
-   [Plusieurs barres d'outils](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> L'Option Barre d'Outil de l'Assistant d'Application.  
 Pour obtenir une seule barre d'outils dotée de boutons par défaut, sélectionnez l'option standard de la barre d'outils d'ancrage dans la page intitulée Fonctionnalités de l'Interface Utilisateur.  Cela ajoute le code à votre application qui :  
  
-   Crée l'objet barre d'outils.  
  
-   Gère la barre d'outils, notamment la possibilité d'ancrage ou de flottaison.  
  
##  <a name="_core_the_toolbar_in_code"></a> La Barre d'Outils dans le Code  
 La barre d'outils est un objet [CToolBar](../mfc/reference/ctoolbar-class.md) déclaré en tant que membre de données de la classe **CMainFrame** de votre application.  En d'autres termes, l'objet barre d'outils est incorporé dans l'objet cadre de fenêtre principale.  Cela signifie que MFC crée la barre d'outils lorsqu'il crée la fenêtre cadre et détruit la barre d'outils lorsqu'il détruit la fenêtre cadre.  La déclaration de classe partielle suivante, pour une application de l'interface à multiples documents \(MDI\), affiche les membres de données pour une barre d'outils incorporée et la barre d'état incorporée.  Il indique également la substitution de la fonction membre `OnCreate`.  
  
 [!code-cpp[NVC_MFCListView#6](../mfc/codesnippet/CPP/toolbar-fundamentals_1.h)]  
  
 La création de la barre d'outils se produit dans **CMainFrame::OnCreate**.  MFC appelle [OnCreate](../Topic/CWnd::OnCreate.md) après avoir créé la fenêtre du cadre mais avant qu'elle soit visible.  Par défaut, `OnCreate` créé par l'Assistant d'Installation effectue les tâches suivantes de la barre d'outils :  
  
1.  Appelle [Créer](../Topic/CToolBar::Create.md) de l'objet `CToolBar` de la fonction membre pour créer l'objet sous\-jacent [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
2.  Appelle [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) pour charger des informations sur les ressources de la barre d'outils.  
  
3.  Les fonctions d'appels pour activer l'ancrage, la flottaison, et les info\-bulles.  Pour plus d'informations sur ces appels, consultez l'article [Ancrage et barres d'outils flottantes](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  L'exemple général [DOCKTOOL](../top/visual-cpp-samples.md) de MFC inclut des figures des barres d'outils anciennes et récentes de MFC.  Les barres d'outils qui utilisent **COldToolbar** requièrent des appels à l'étape 2 vers `LoadBitmap` \(au lieu de `LoadToolBar`\) et `SetButtons`.  Les nouvelles barres d'outils nécessitent des appels à `LoadToolBar`.  
  
 L'ancrage, la flottaison, et les appels d'info\-bulles sont facultatifs.  Vous pouvez supprimer ces lignes de `OnCreate` si vous le désirez.  Le résultat est une barre d'outils qui reste fixe, privée de flottaison ou d'ancrage et dont il est impossible d'afficher les info\-bulles.  
  
##  <a name="_core_editing_the_toolbar_resource"></a> Modifier la Ressource Barre d'Outils  
 La barre d'outils par défaut que vous obtenez avec l'Assistant d'Application est basée sur une ressource personnalisée **RT\_TOOLBAR**, introduite dans la version 4,0 de MFC.  Vous pouvez modifier cette ressource grâce à [toolbar editor](../mfc/toolbar-editor.md).  L'éditeur vous permet d'ajouter, supprimer, et de réorganiser les boutons simplement.  Il contient un éditeur graphique pour les boutons qui est très semblable à l'éditeur graphique usuel dans Visual C\+\+.  Si vous avez modifié des barres d'outils avec une version antérieure de Visual C\+\+, vous trouverez la tâche beaucoup plus simple à présent.  
  
 Pour connecter un bouton de la barre d'outils à commande, vous donnez au bouton un ID de commande, tel que `ID_MYCOMMAND`.  Spécifiez l'ID de commande dans la page propriétés du bouton dans l'éditeur de barre d'outils.  Créez ensuite une fonction responsable de la commande \(voir [Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md) pour plus d'informations\).  
  
 Les nouvelles fonctions membres [CToolBar](../mfc/reference/ctoolbar-class.md) travaillent avec la ressource **RT\_TOOLBAR**.  [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) remplace maintenant [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) pour charger la bitmap des images de boutons de la barre d'outils, et [SetButtons](../Topic/CToolBar::SetButtons.md) pour définir les styles les boutons et pour connecter les boutons avec des images bitmap.  
  
 Pour plus d'informations sur l'utilisation de l'éditeur de barre d'outils, consultez [Éditeur de barres d'outils](../mfc/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a> Plusieurs Barres d'Outils  
 L'Assistant d'Application fournit une barre d'outils par défaut.  Si vous avez besoin de plusieurs barre d'outils dans votre application, vous pouvez ajuster votre code pour des d'outils supplémentaires en utilisant le code généré par l'Assistant d'Application pour la barre d'outil par défaut.  
  
 Si vous souhaitez afficher une barre d'outils comme résultat d'une commande, vous aurez besoin de :  
  
-   Créer une nouvelle ressource barre d'outils avec l'éditeur de barre d'outils et la charger dans `OnCreate` avec la fonction membre [LoadToolbar](../Topic/CToolBar::LoadToolBar.md).  
  
-   Incluez un nouvel objet [CToolBar](../mfc/reference/ctoolbar-class.md) dans votre classe cadre de fenêtre principale.  
  
-   Effectuer les appels de fonctions appropriés dans `OnCreate` pour l'ancrage ou la flottaison de la barre d'outils, définissez ses styles, et ainsi de suite.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Implémentation de la barre d'outils de MFC \(informations générales sur les barres d'outils\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Ancrer et rendre flottantes les barres d'outils](../mfc/docking-and-floating-toolbars.md)  
  
-   [Info\-bulles de barre d'outils](../mfc/toolbar-tool-tips.md)  
  
-   Les classes [CToolBar](../mfc/reference/ctoolbar-class.md) et [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Utilisation du contrôle de barre d'outils](../mfc/working-with-the-toolbar-control.md)  
  
-   [Utilisation de vos anciennes barres d'outils](../mfc/using-your-old-toolbars.md)  
  
## Voir aussi  
 [Implémentation de la barre d'outils MFC](../mfc/mfc-toolbar-implementation.md)