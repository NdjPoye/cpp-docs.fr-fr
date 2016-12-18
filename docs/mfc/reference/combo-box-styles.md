---
title: "Styles de zone de liste modifiable | Microsoft Docs"
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
  - "CBS_LOWERCASE"
  - "CBS_SORT"
  - "CBS_OWNERDRAWVARIABLE"
  - "CBS_OEMCONVERT"
  - "CBS_AUTOHSCROLL"
  - "CBS_NOINTEGRALHEIGHT"
  - "CBS_SIMPLE"
  - "CBS_DROPDOWNLIST"
  - "CBS_DROPDOWN"
  - "CBS_UPPERCASE"
  - "CBS_HASSTRINGS"
  - "CBS_DISABLENOSCROLL"
  - "CBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBS_OWNERDRAWVARIABLE (constante)"
  - "CBS_NOINTEGRALHEIGHT (constante)"
  - "CBS_SIMPLE (constante)"
  - "CBS_AUTOHSCROLL (constante)"
  - "CBS_OEMCONVERT (constante)"
  - "CBS_DISABLENOSCROLL (constante)"
  - "CBS_HASSTRINGS (constante)"
  - "CBS_LOWERCASE (constante)"
  - "CBS_SORT (constante)"
  - "CBS_DROPDOWN (constante)"
  - "CBS_OWNERDRAWFIXED (constante)"
  - "zones de liste modifiable, styles"
  - "CBS_UPPERCASE (constante)"
  - "CBS_DROPDOWNLIST (constante)"
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles de zone de liste modifiable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les styles de zone de liste modifiable suivants sont disponibles dans MFC.  
  
-   **CBS\_AUTOHSCROLL** : fait défiler automatiquement le texte du contrôle d’édition vers la droite quand l’utilisateur tape un caractère à la fin d’une ligne. Si ce style n’est pas défini, seul le texte qui rentre dans la limite rectangulaire est autorisé.  
  
-   **CBS\_DISABLENOSCROLL** : la zone de liste affiche une barre de défilement verticale désactivée quand elle ne contient pas suffisamment d’éléments pour effectuer un défilement. Sans ce style, la barre de défilement est masquée lorsque la zone de liste ne contient pas assez d'éléments.  
  
-   **CBS\_DROPDOWN** : est semblable à **CBS\_SIMPLE**, à la différence près que la zone de liste ne s’affiche que si l’utilisateur sélectionne une icône à côté du contrôle d’édition.  
  
-   **CBS\_DROPDOWNLIST** : est semblable à **CBS\_DROPDOWN**, à la différence près que le contrôle d’édition est remplacé par un élément de texte statique qui affiche la sélection actuelle dans la zone de liste.  
  
-   **CBS\_HASSTRINGS** : une zone de liste modifiable owner\-draw contient des éléments se composant de chaînes. La zone de liste modifiable contient la mémoire et les pointeurs des chaînes, ce qui permet à l’application d’utiliser la fonction membre `GetText` pour récupérer le texte d’un élément particulier.  
  
-   **CBS\_LOWERCASE** : convertit en minuscules tout le texte dans le champ de sélection et la liste.  
  
-   **CBS\_NOINTEGRALHEIGHT** : spécifie que la taille de la zone de liste modifiable correspond exactement à la taille spécifiée par l’application au moment de la création de la zone de liste modifiable. Généralement, Windows redimensionne une zone de liste modifiable pour qu’elle n’affiche aucun élément de manière partielle.  
  
-   **CBS\_OEMCONVERT** : convertit le jeu de caractères ANSI du texte entré dans le contrôle d’édition de la zone de liste modifiable en jeu de caractères OEM, puis le reconvertit en ANSI. Cela garantit la conversion appropriée des caractères quand l’application appelle la fonction Windows `AnsiToOem` pour convertir une chaîne ANSI dans la zone de liste modifiable en caractères OEM. Ce style, particulièrement utile pour les zones de liste modifiable contenant des noms de fichiers, s’applique uniquement aux zones de liste modifiable créées avec les styles **CBS\_SIMPLE** ou **CBS\_DROPDOWN**  
  
-   **CBS\_OWNERDRAWFIXED** : le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments de la zone de liste ont tous la même hauteur.  
  
-   **CBS\_OWNERDRAWVARIABLE** : le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments de la zone de liste varient en hauteur.  
  
-   **CBS\_SIMPLE** : la zone de liste est affichée en permanence. La sélection actuelle dans la zone de liste s’affiche dans le contrôle d’édition.  
  
-   **CBS\_SORT** : trie automatiquement les chaînes entrées dans la zone de liste.  
  
-   **CBS\_UPPERCASE** : convertit en majuscules tout le texte dans le champ de sélection et la liste.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create](../Topic/CComboBox::Create.md)   
 [Combo Box Styles](_win32_combo_box_styles)