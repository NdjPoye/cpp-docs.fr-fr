---
title: "Ancrer et rendre flottantes les barres d&#39;outils | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBRS_SIZE_DYNAMIC"
  - "CBRS_SIZE_FIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBRS_ALIGN_ANY (constante)"
  - "CBRS_SIZE_DYNAMIC (constante)"
  - "CBRS_SIZE_FIXED (constante)"
  - "barres d'outils de taille fixe"
  - "palettes flottantes"
  - "barres d'outils flottantes"
  - "fenêtres frame, ancrage de barre d'outils"
  - "palettes, flottant"
  - "taille"
  - "taille, barres d'outils"
  - "contrôles de barre d'outils (MFC), inclusion dans un wrapper"
  - "barres d'outils (C++), fixer"
  - "barres d'outils (C++), flottant"
  - "barres d'outils (C++), taille"
  - "barres d'outils (C++), inclusion dans un wrapper"
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ancrer et rendre flottantes les barres d&#39;outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC supporte les barres d'outils ancrables.  Il est possible d'attacher une barre d'outils ancrable à l'un des côtés de sa fenêtre parente mais aussi de la détacher, ou de la laisser flotter, dans sa propre fenêtre mini\-frame.  Cet article explique comment utiliser les barres d'outils ancrables dans vos applications.  
  
 Si vous utilisez l'Assistant d'Application pour générer la structure de votre application, vous êtes invité à sélectionner si vous souhaitez les barres d'outils ancrables.  Par défaut, l'Assistant d'Application génère un code qui exécute les trois actions nécessaires pour placer une barre d'outils ancrable dans votre application :  
  
-   [Activez l'ancrage dans une fenêtre cadre](#_core_enabling_docking_in_a_frame_window).  
  
-   [Activez l'extrémité d'une barre d'outils](#_core_enabling_docking_for_a_toolbar).  
  
-   [Ancrez la barre d'outil \(à la fenêtre cadre\)](#_core_docking_the_toolbar).  
  
 Si l'une de ces étapes est manquante, l'application affiche une barre d'outils standard.  Les deux dernières étapes doivent être réalisées pour chacune des barres d'outils ancrables de votre application.  
  
 Les autres rubriques traitées dans cet article sont les suivantes :  
  
-   [Flottement de la barre d'outils](#_core_floating_the_toolbar)  
  
-   [Redimensionner dynamiquement la barre d'outils](#_core_dynamically_resizing_the_toolbar)  
  
-   [Définir les positions d'enveloppe d'une barre d'outils de style fixe](#_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar)  
  
 Consultez l'exemple général Mfc [DOCKTOOL](../top/visual-cpp-samples.md) pour voir des exemples.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> Activer l'ancrage dans une fenêtre cadre  
 Pour ancrer des barres d'outils dans une fenêtre cadre, la fenêtre cadre \(ou destination\) doit être activée pour permettre à l'ancrage.  Cette opération s'effectue à l'aide de la fonction [CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md), qui accepte un paramètre de `DWORD` qui est un ensemble de bits de styles qui indique quel côté de la fenêtre cadre reçoit l'ancrage.  Si une barre d'outils est sur le point d'être ancrée et qu'il y a plusieurs côtés à laquelle elle peut être ancrée, les côtés affichés dans le paramètre transmis à `EnableDocking` sont utilisés dans l'ordre suivant : supérieure, inférieure, gauche, droite.  Si vous souhaitez pouvoir ancrer des barres de contrôle n'importe où, passez `CBRS_ALIGN_ANY` à `EnableDocking`.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> Activer l'extrémité d'une barre d'outils  
 Après avoir préparé la destination d'ancrage, vous devez préparer la barre d'outils \(ou la source\) de la même manière.  Appelez [CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md) pour chaque barre d'outils que vous souhaitez ancrer, en spécifiant le ou les côtés de destination sur laquelle la barre d'outils doit s'ancrer.  Si aucun des côtés spécifiés dans l'appel à `CControlBar::EnableDocking` ne correspond aux côtés activés pour l'ancrage dans la fenêtre frame, la barre d'outils ne peut pas être ancrée ; elle flottera.  Dès qu'elle flotte, elle reste alors une barre d'outils flottante, incapable de s'ancrer à la fenêtre frame.  
  
 Si l'effet souhaité est une barre d'outils de flottement définitivement, appelez `EnableDocking` avec un paramètre de 0.  Appelez ensuite [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md).  La barre d'outils reste flottante, définitivement incapable de s'ancrer nulle part.  
  
##  <a name="_core_docking_the_toolbar"></a> Ancrer la barre d'outils  
 L'infrastructure appelle [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md) lorsque l'utilisateur tente de supprimer la barre d'outils d'un côté de la fenêtre de cadre permettant l'ancrage.  
  
 En outre, vous pouvez appeler cette fonction à tout moment pour ancrer des barres de contrôles dans la fenêtre cadre.  Ceci est généralement effectué pendant l'initialisation.  Plusieurs barres d'outils peuvent être ancrée à un côté spécifique de la fenêtre cadre.  
  
##  <a name="_core_floating_the_toolbar"></a> Flottement de la Barre d'outils  
 Détacher une barre d'outils ancrable dans la fenêtre cadre est appelé faire flotter la barre d'outils.  Appelez [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md) pour cela.  Spécifiez la barre d'outils que vous voulez faire flotter, le point où elle doit se placer, et un style d'alignement qui détermine si la barre d'outils flottante est horizontale ou verticale.  
  
 L'infrastructure appelle cette fonction lorsqu'un utilisateur fait glisser une barre d'outils en dehors de son emplacement ancré et la lâche dans un emplacement où l'ancrage n'est pas activé.  Cela peut être n'importe où à l'intérieur ou à l'extérieur de la fenêtre cadre.  Comme avec `DockControlBar`, vous pouvez appeler cette fonction pendant l'initialisation.  
  
 L'implémentation MFC des barres d'outils ancrables ne présente pas certaines des fonctionnalités étendues disponibles dans des applications qui prennent en charge les barres d'outils ancrables.  Des fonctionnalités telles que les barres d'outils personnalisables ne sont pas fournies.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> Redimensionner dynamiquement la barre d'outils  
 À compter de la version 4,0 de Visual C\+\+, vous pouvez rendre possible aux utilisateurs de votre application de redimensionner les barres d'outils flottantes dynamiquement.  En règle générale, une barre d'outils a une longue forme linéaire, affichée horizontalement.  Vous pouvez modifier la forme de la barre d'outils et son orientation.  Par exemple, lorsque l'utilisateur accueille une barre d'outils sur l'un des côtés verticaux de la fenêtre cadre, elle se met en page de façon verticale.  Il est également possible de reformer la barre d'outils en un rectangle à plusieurs lignes de boutons.  
  
 Vous pouvez :  
  
-   Spécifiez le dimensionnement dynamique comme caractéristique de la barre d'outils.  
  
-   Spécifiez le dimensionnement fixe comme caractéristique de la barre d'outils.  
  
 Pour assurer la prise en charge, il existe deux styles de la barre d'outils à utiliser dans les appels à la fonction membre [CToolBar::Create](../Topic/CToolBar::Create.md).  Il s'agit des éléments suivants :  
  
-   La barre de contrôle de **CBRS\_SIZE\_DYNAMIC** est dynamique.  
  
-   La barre de contrôle de **CBRS\_SIZE\_FIXED** est fixe.  
  
 Le style de taille dynamique permet à l'utilisateur de redimensionner la barre d'outils lorsqu'elle flotte, mais pas lorsqu'elle est ancrée.  La barre d'outils « enveloppe » ce qui est nécessaire pour se déformer lorsque l'utilisateur fait glisser ses extrémités.  
  
 Le style de taille fixe conserve les états d'enveloppe d'une barre d'outils, en fixant la position des boutons de chaque colonne.  L'utilisateur de votre application ne peut pas modifier la forme de la barre d'outils.  La barre d'outil enveloppe aux endroits désignés, tels que les emplacements des séparateurs entre les boutons.  Elle maintient cette forme si la barre d'outils est ancrée ou flotte.  Le résultat est une palette fixe avec plusieurs colonnes de boutons.  
  
 Vous pouvez également utiliser [CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) pour retourner un état et un style pour les boutons de les barres d'outils.  Le style d'un bouton indique comment le bouton s'affiche et comment il répond à une entrée utilisateur ; l'état indique si le bouton est dans un état encapsulé.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar"></a> Définir les positions d'enveloppe d'une barre d'outils de style fixe  
 Pour une barre d'outils avec le style de taille fixe, désignez les indexes de boutons de la barre d'outils dans lesquels la barre d'outils s'encapsulera.  Le code suivant indique comment procéder dans la substitution de `OnCreate` dans votre fenêtre cadre principale :  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/CPP/docking-and-floating-toolbars_1.cpp)]  
  
 L'exemple Général de MFC [DOCKTOOL](../top/visual-cpp-samples.md) montre comment utiliser les fonctions membres des classes [CControlBar](../mfc/reference/ccontrolbar-class.md) et [CToolBar](../mfc/reference/ctoolbar-class.md) pour gérer la mise en page dynamique d'une barre d'outils.  Consultez le fichier EDITBAR.CPP dans DOCKTOOL.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Notions de base de barre d'outils](../mfc/toolbar-fundamentals.md)  
  
-   [Info\-bulles de barre d'outils](../mfc/toolbar-tool-tips.md)  
  
-   [Utilisation de vos anciennes barres d'outils](../mfc/using-your-old-toolbars.md)  
  
## Voir aussi  
 [Implémentation de la barre d'outils MFC](../mfc/mfc-toolbar-implementation.md)