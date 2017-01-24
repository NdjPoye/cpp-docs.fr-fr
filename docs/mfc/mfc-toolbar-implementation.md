---
title: "Impl&#233;mentation de la barre d&#39;outils MFC | Microsoft Docs"
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
  - "bitmaps (C++), barre d'outils"
  - "boutons (C++), barres d'outils MFC"
  - "CToolBar (classe), créer des barres d'outils"
  - "CToolBarCtrl (classe), implémenter des barres d'outils"
  - "barres d'outils ancrées"
  - "barres d'outils flottantes"
  - "barres d'outils MFC"
  - "info-bulles (C++), activer"
  - "contrôles de barre d'outils (MFC)"
  - "barres d'outils (C++)"
  - "barres d'outils (C++), créer"
  - "barres d'outils (C++), fixer"
  - "barres d'outils (C++), flottant"
  - "barres d'outils (C++), implémenter des barres d'outils MFC"
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impl&#233;mentation de la barre d&#39;outils MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une barre d'outils est une [barre de contrôles](../mfc/control-bars.md) qui contient les images bitmap des contrôles.  Ces images peuvent se comporter comme des boutons poussoirs, des cases à cocher, ou des cases d'option.  MFC fournit la classe [CToolbar](../mfc/reference/ctoolbar-class.md) pour gérer les barres d'outils.  
  
 Si vous l'activez, les utilisateurs des barres d'outils MFC peuvent les ancrer au bord d'une fenêtre ou les faire flotter n'importe où dans la fenêtre d'application.  MFC ne prend pas en charge les barres d'outils personnalisables telles que celles de l'environnement de développement.  
  
 MFC prend également en charge des infos\-bulles : petites fenêtres indépendantes qui décrivent la fonction d'un bouton de barre d'outils lorsque vous positionnez le pointeur de la souris sur le bouton.  Par défaut, lorsque l'utilisateur appuie sur un bouton de barre d'outils, une chaîne d'état s'affiche dans la barre d'état \(si elle existe\).  Activez la mise à jour de la barre d'état par "survol" pour afficher la chaîne d'état lorsque la souris est positionnée sur le bouton sans cliquer dessus.  
  
> [!NOTE]
>  En ce qui concerne la version 4.0 de MFC, les barres d'outils et les info\-bulles sont implémentées à l'aide de Windows 95 et de ses fonctionnalités ultérieure au lieu des précédentes implémentations spécifiques aux MFC.  
  
 Pour la compatibilité descendante, MFC conserve l'ancienne implémentation de barres d'outils dans la classe **COldToolBar**.  La documentation pour les versions antérieures de MFC décrivent **COldToolBar** sous `CToolBar`.  
  
 Créez la première barre d'outils dans votre programme en sélectionnant l'option Barre d'outil de l'Assistant d'application.  Créez également des barres d'outils supplémentaires.  
  
 Les rubriques suivantes sont présentées dans cet article :  
  
-   [boutons de barre d'outils](#_core_toolbar_buttons)  
  
-   [Ancrer et rendre flottantes les barres d'outils](#_core_docking_and_floating_toolbars)  
  
-   [Barres d'outils et info\-bulles](#_core_toolbars_and_tool_tips)  
  
-   [Les classes CToolBar et CToolBarCtrl](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [La barre d'outils Image Bitmap](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> Boutons de barre d'outils  
 Les boutons d'une barre d'outils sont analogues aux éléments d'un menu.  Les deux types d'objets utilisateur\-interface génèrent des commandes, que votre programme gère en fournissant des fonctions de gestion.  Souvent les boutons de barre d'outils doublent les fonctionnalités des commandes de menu, fournissant aux mêmes fonctionnalités une autre interface utilisateur.  Une telle duplication est organisée simplement en donnant à l'élément de menu et au bouton la même ID.  
  
 Vous pouvez faire en sorte que les boutons d'une barre d'outils apparaissent et se comportent comme des boutons poussoirs, des cases à cocher, ou des cases d'option.  Pour plus d'informations, consultez la classe [CToolBar](../mfc/reference/ctoolbar-class.md).  
  
##  <a name="_core_docking_and_floating_toolbars"></a> Ancrer et rendre les barres d'outils flottantes  
 Une barre d'outils MFC peut :  
  
-   Restez stationnaire le long d'un côté de sa fenêtre parente.  
  
-   Être glissée et « ancrée, » ou attachée, par l'utilisateur à n'importe quel côté ou côtés de la fenêtre parente que vous spécifiez.  
  
-   Être « flottante, » ou détaché du cadre de la fenêtre, dans sa propre fenêtre mini\-frame afin que l'utilisateur puisse la déplacer à n'importe quelle position pratique.  
  
-   Être redimensionnée pendant qu'elle flotte.  
  
 Pour plus d'informations, consultez l'article [Ancrage et barres d'outils flottante](../mfc/docking-and-floating-toolbars.md).  
  
##  <a name="_core_toolbars_and_tool_tips"></a> Barres d'outils et info\-bulles  
 Les barres d'outils MFC peuvent également servir pour afficher des « info\-bulles » — petites fenêtres indépendantes dont le texte décrit la fonction d'un bouton de barre d'outils  Lorsque l'utilisateur déplace la souris au dessus d'un bouton de barre d'outils, la fenêtre d'info\-bulle s'affiche pour fournir une indication.  Pour plus d'informations, consultez l'article [Info\-bulles de barre d'outils](../mfc/toolbar-tool-tips.md).  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> Les classes CToolBar et CToolBarCtrl  
 Vous gérez les barres d'outils de votre application via la classe [CToolBar](../mfc/reference/ctoolbar-class.md).  Concernant la version 4.0 des MFC, `CToolBar` a été réimplémenté pour utiliser la barre d'outil de contrôle commun disponible sous Windows 95 ou ultérieur et Windows NT version 3,51 ou ultérieure.  
  
 Cette réimplémentation entraîne moins de code MFC pour les barres d'outils, car MFC utilise la prise en charge du système d'exploitation.  La réimplémentation améliore également la capacité.  Utilisez les fonctions membres de `CToolBar` pour manipuler vos barres d'outils, ou vous pouvez obtenir une référence à l'objet sous\-jacent d' [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) et appeler ses fonctions membres pour la personnalisation et pour des fonctionnalités supplémentaires.  
  
> [!TIP]
>  Si vous avez investi fortement dans l'implémentation MFC antérieure d' `CToolBar`, cette prise en charge est toujours disponible.  Consultez l'article [Utilisation des anciennes barres d'outils](../mfc/using-your-old-toolbars.md).  
  
 Consultez également l'exemple général MFC [DOCKTOOL](../top/visual-cpp-samples.md).  
  
##  <a name="_core_the_toolbar_bitmap"></a> La barre d'outils Image Bitmap  
 Une fois construit, un objet `CToolBar` crée l'image de barre d'outils en chargeant une seule image bitmap qui contient une image pour chaque bouton.  L'Assistant d'application crée une bitmap de barre d'outils standard que vous pouvez personnaliser avec Visual C\+\+ [éditeur de barre d'outils](../mfc/toolbar-editor.md).  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Notions de base de barre d'outils](../mfc/toolbar-fundamentals.md)  
  
-   [Ancrer et rendre flottantes les barres d'outils](../mfc/docking-and-floating-toolbars.md)  
  
-   [Info\-bulles de barre d'outils](../mfc/toolbar-tool-tips.md)  
  
-   [Utilisation du contrôle de barre d'outils](../mfc/working-with-the-toolbar-control.md)  
  
-   [Utilisation de vos anciennes barres d'outils](../mfc/using-your-old-toolbars.md)  
  
-   Les classes [CToolBar](../mfc/reference/ctoolbar-class.md) et [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
## Voir aussi  
 [Barres d'outils](../mfc/toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)