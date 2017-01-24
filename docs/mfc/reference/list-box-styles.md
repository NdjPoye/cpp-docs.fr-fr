---
title: "Styles de zone de liste | Microsoft Docs"
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
  - "LBS_STANDARD"
  - "LBS_NODATA"
  - "LBS_OWNERDRAWVARIABLE"
  - "LBS_EXTENDEDSEL"
  - "LBS_USETABSTOPS"
  - "LBS_WANTKEYBOARDINPUT"
  - "LBS_NOTIFY"
  - "LBS_DISABLENOSCROLL"
  - "LBS_HASSTRINGS"
  - "LBS_NOREDRAW"
  - "LBS_NOSEL"
  - "LBS_NOINTEGRALHEIGHT"
  - "LBS_MULTICOLUMN"
  - "LBS_SORT"
  - "LBS_MULTIPLESEL"
  - "LBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LBS_DISABLENOSCROLL (constante)"
  - "LBS_EXTENDEDSEL (constante)"
  - "LBS_HASSTRINGS (constante)"
  - "LBS_MULTICOLUMN (constante)"
  - "LBS_MULTIPLESEL (constante)"
  - "LBS_NODATA (constante)"
  - "LBS_NOINTEGRALHEIGHT (constante)"
  - "LBS_NOREDRAW (constante)"
  - "LBS_NOSEL (constante)"
  - "LBS_NOTIFY (constante)"
  - "LBS_OWNERDRAWFIXED (constante)"
  - "LBS_OWNERDRAWVARIABLE (constante)"
  - "LBS_SORT (constante)"
  - "LBS_STANDARD (constante)"
  - "LBS_USETABSTOPS (constante)"
  - "LBS_WANTKEYBOARDINPUT (constante)"
  - "zones de liste, styles"
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles de zone de liste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **LBS\_DISABLENOSCROLL** La fenêtre des listes affiche une barre de défilement verticale désactivée lorsque la fenêtre des listes ne contient pas assez d'éléments pour faire défiler.  Sans ce style, la barre de défilement est masquée lorsque la fenêtre de listes ne contient pas assez d'éléments.  
  
-   **LBS\_EXTENDEDSEL** L'utilisateur peut sélectionner plusieurs éléments à l'aide de la touche MAJ et de la souris ou les combinaisons de touches spéciales.  
  
-   **LBS\_HASSTRINGS** Spécifie une zone de liste owner\-draw qui contient des éléments composé de chaînes.  La fenêtre de liste contient la mémoire et les pointeurs pour les chaînes afin que l'application puisse utiliser la méthode `GetText` pour récupérer le texte d'un élément particulier.  
  
-   **LBS\_MULTICOLUMN** Indique une zone de liste multicolonne avec un défilement horizontal.  La méthode `SetColumnWidth` définit la largeur des colonnes.  
  
-   **LBS\_MULTIPLESEL** La sélection de chaîne est basculée chaque fois que l'utilisateur clique ou double\-clique sur la chaîne.  Plusieurs chaînes peuvent être sélectionnées.  
  
-   **LBS\_NODATA** Spécifie une zone de liste sans données.  Spécifiez ce style lorsque le nombre d'éléments dans la zone de liste dépasse 1000.  Une zone de liste sans données doit également disposer du style **LBS\_OWNERDRAWFIXED**, mais ne doit pas être le style **LBS\_SORT** ou **LBS\_HASSTRINGS**.  
  
     Une zone de liste sans données s'apparente à une zone de liste dessinée par le propriétaire sauf qu'elle ne contient aucune chaîne ou donnée bitmap comme élément.  Les commandes d'ajout, insertion, et suppresion d'un élément ignorent toutes les données d'un élément donné; les requêtes de recherche d'une chaîne dans la zone de liste échouent toujours.  Le système envoie le message `WM_DRAWITEM` dans la fenêtre propriétaire lorsqu'un élément doit être dessiné.  Le membre itemID de la structure `DRAWITEMSTRUCT` passée avec le message `WM_DRAWITEM` spécifie le numéro de ligne de l'élément à dessiner.  Une zone de liste sans données n'envoie pas un message `WM_DELETEITEM`.  
  
-   **LBS\_NOINTEGRALHEIGHT** La taille de la zone de liste est exactement la taille spécifiée par l'application lors de la création de la zone de liste.  Généralement, Windows redimensionne une zone de liste afin que la zone de liste n'affiche pas les éléments partiels.  
  
-   **LBS\_NOREDRAW** L'affichage de la zone de liste n'est pas mis à jour lorsque des modifications sont apportées.  Ce style peut être modifiée à tout moment en envoyant un message **WM\_SETREDRAW**.  
  
-   **LBS\_NOSEL** Spécifie que la zone de liste contient des éléments qui peuvent être consultés mais non sélectionnés.  
  
-   **LBS\_NOTIFY** La fenêtre parente reçoit un message d'entrée lorsque l'utilisateur clique ou double\-clique sur une chaîne.  
  
-   **LBS\_OWNERDRAWFIXED** Le propriétaire de la fenêtre de liste est chargé de dessiner son contenu ; les éléments de la fenêtre de liste sont tous de la même hauteur.  
  
-   **LBS\_OWNERDRAWVARIABLE** Le propriétaire de la fenêtre de liste est chargé de dessiner son contenu ; les éléments de la zone de liste sont variables au niveau de la hauteur.  
  
-   **LBS\_SORT** Les chaînes dans la zone de liste sont triées par ordre alphabétique.  
  
-   **LBS\_STANDARD** Les chaînes dans la zone de liste sont triées par ordre alphabétique, et la fenêtre parente reçoit un message d'entrée lorsque l'utilisateur clique sur ou double\-cliquez sur une chaîne.  La zone de liste contient les bordures sur tous les côtés.  
  
-   **LBS\_USETABSTOPS** Permet à une zone de liste de reconnaître et développer des tabulations lors du traçage des chaînes.  Les positions d'onglet par défaut sont 32 unités de la boîte de dialogue. \(L'unité de la boîte de dialogue est une distance horizontale ou verticale.  Une unité de la boîte de dialogue horizontale est égale à un quart de l'unité actuelle de largeur de base de dialogue.  Les unités de dialogue sont calculées en fonction de la hauteur et la largeur de la police système actuelle.  La fonction Windows **GetDialogBaseUnits** retourne les unités de base actuelles de dialogue en pixels.\) Ce style ne doit pas être utilisé avec **LBS\_OWNERDRAWFIXED**.  
  
-   **LBS\_WANTKEYBOARDINPUT** Le propriétaire de la zone de liste reçoit des messages `WM_VKEYTOITEM` ou `WM_CHARTOITEM` chaque fois que l'utilisateur appuie sur une touche lorsque la zone de liste est active en entrée.  Cela permet à une application d'effectuer un traitement spécial sur l'entrée de clavier.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../Topic/CListBox::Create.md)   
 [List Box Styles](http://msdn.microsoft.com/library/windows/desktop/bb775149)