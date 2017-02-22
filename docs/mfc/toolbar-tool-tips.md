---
title: "Info-bulles de barre d&#39;outils | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBRS_FLYBY (constante)"
  - "CBRS_TOOLTIPS (constante)"
  - "mises à jour de barre d'état flyby"
  - "barres d'état, info-bulles"
  - "info-bulles (C++)"
  - "info-bulles (C++), activer"
  - "info-bulles (C++), ajouter du texte"
  - "mises à jour"
  - "mises à jour, messages de barre d'état"
  - "mettre à jour les messages de barre d'état"
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Info-bulles de barre d&#39;outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les info\-bulles sont les fenêtres pop\-up minuscules présentant la description courte de l'objectif d'un bouton de la barre d'outils lorsque vous placez la souris sur un bouton pendant un certain temps.  Lorsque vous créez une application avec l'Application qui a une barre d'outils, la prise en charge de l'info\-bulle est fournie pour vous.  Cet article explique d'une part la prise en charge des info\-bulles créée par l'Application et d'autre part comment ajouter la prise en charge de l'info\-bulle à votre application.  
  
 Cet article explique:  
  
-   [Activer les info\-bulles](#_core_activating_tool_tips)  
  
-   [Le survol des mises à jour des barres de statuts.](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a> Activer les outils conseils.  
 Pour activer les info\-bulles dans votre application, vous devez effectuer deux choses :  
  
-   Ajoutez le style d' `CBRS_TOOLTIPS` aux autres styles \(tels que **WS\_CHILD**, **WS\_VISIBLE**, et d'autres styles de **CBRS\_** \) transmis comme paramètre d' `dwStyle` à la fonction d' [CToolBar::Create](../Topic/CToolBar::Create.md) ou dans [SetBarStyle](../Topic/CControlBar::SetBarStyle.md).  
  
-   Conformément à la procédure ci\-dessous, ajoutez le texte à l'extrémité de la barre d'outils, séparé par un caractère de saut de ligne \("\\ n"\), à la ressource de chaîne contenant l'invite de ligne de commande pour la commande dans la barre d'outils.  La ressource de chaîne partage l'ID du bouton de la barre d'outils.  
  
#### Pour ajouter le texte info\-bulle  
  
1.  Lorsque vous modifiez la barre d'outils dans l'éditeur de barre d'outils, ouvrez la fenêtre de **Toolbar Button Properties** pour un bouton donné.  
  
2.  Dans la zone de **Demander** , spécifiez le texte qui doit s'afficher dans l'info\-bulle pour ce bouton.  
  
> [!NOTE]
>  Définir le texte comme une propriété de bouton dans l'éditeur de barre d'outils remplace alors la procédure précédente, dans laquelle vous deviez ouvrir et modifier la ressource de chaîne.  
  
 Si une barre de contrôle avec des info\-bulles activées a des contrôles parentaux situés dessus, la barre de contrôle affiche une info\-bulle pour chaque contrôle parental dans la barre de contrôle tant qu'elle répond aux critères suivants :  
  
-   L'ID de contrôle n'est pas \-1.  
  
-   L'entrée de chaîne avec le même ID que le contrôle parental dans le fichier de ressources a une plage de l'info\-bulle.  
  
##  <a name="_core_fly_by_status_bar_updates"></a> Survol les mises à jour de barre d'état  
 Une fonction liée aux info\-bulles est "survol" de la mise à jour de la barre d'état.  Par défaut, le message dans la barre d'état décrit un bouton particulier de la barre d'outils lorsque le bouton est actionné.  En incluant `CBRS_FLYBY` dans la liste des styles passés à `CToolBar::Create`, vous pouvez mettre à jour ces messages lorsque le curseur de la souris passe sur la barre d'outils fichier sans réellement cliquer sur le bouton.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Implémentation de la barre d'outils de MFC \(des informations générales sur les barres d'outils\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Ancrer et rendre flottantes les barres d'outils](../mfc/docking-and-floating-toolbars.md)  
  
-   Les classes [CToolBar](../mfc/reference/ctoolbar-class.md) et [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Utilisation du contrôle de barre d'outils](../mfc/working-with-the-toolbar-control.md)  
  
-   [Utilisation de vos anciennes barres d'outils](../mfc/using-your-old-toolbars.md)  
  
## Voir aussi  
 [Implémentation de la barre d'outils MFC](../mfc/mfc-toolbar-implementation.md)