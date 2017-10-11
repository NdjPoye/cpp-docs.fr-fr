---
title: "Styles de zone de liste déroulante | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBS_LOWERCASE
- CBS_SORT
- CBS_OWNERDRAWVARIABLE
- CBS_OEMCONVERT
- CBS_AUTOHSCROLL
- CBS_NOINTEGRALHEIGHT
- CBS_SIMPLE
- CBS_DROPDOWNLIST
- CBS_DROPDOWN
- CBS_UPPERCASE
- CBS_HASSTRINGS
- CBS_DISABLENOSCROLL
- CBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- CBS_OWNERDRAWVARIABLE constant [MFC]
- CBS_NOINTEGRALHEIGHT constant [MFC]
- CBS_SIMPLE constant [MFC]
- CBS_AUTOHSCROLL constant [MFC]
- CBS_OEMCONVERT constant [MFC]
- CBS_DISABLENOSCROLL constant [MFC]
- CBS_HASSTRINGS constant [MFC]
- CBS_LOWERCASE constant [MFC]
- CBS_SORT constant [MFC]
- CBS_DROPDOWN constant [MFC]
- CBS_OWNERDRAWFIXED constant [MFC]
- combo boxes [MFC], styles
- CBS_UPPERCASE constant [MFC]
- CBS_DROPDOWNLIST constant
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 52cfd21df2f0f72da10589745fb3a8be3e0b24e1
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="combo-box-styles"></a>Styles de zone de liste modifiable
Les styles de zone de liste modifiable suivants sont disponibles dans MFC.  
  
-   **CBS_AUTOHSCROLL** : fait défiler automatiquement le texte du contrôle d’édition vers la droite quand l’utilisateur tape un caractère à la fin d’une ligne. Si ce style n’est pas défini, seul le texte qui rentre dans la limite rectangulaire est autorisé.  
  
-   **CBS_DISABLENOSCROLL** : la zone de liste affiche une barre de défilement verticale désactivée quand elle ne contient pas suffisamment d’éléments pour effectuer un défilement. Sans ce style, la barre de défilement est masquée lorsque la zone de liste ne contient pas assez d'éléments.  
  
-   **CBS_DROPDOWN** : est semblable à **CBS_SIMPLE**, à la différence près que la zone de liste ne s’affiche que si l’utilisateur sélectionne une icône à côté du contrôle d’édition.  
  
-   **CBS_DROPDOWNLIST** : est semblable à **CBS_DROPDOWN**, à la différence près que le contrôle d’édition est remplacé par un élément de texte statique qui affiche la sélection actuelle dans la zone de liste.  
  
-   **CBS_HASSTRINGS** : une zone de liste modifiable owner-draw contient des éléments se composant de chaînes. La zone de liste modifiable contient la mémoire et les pointeurs des chaînes, ce qui permet à l’application d’utiliser la fonction membre `GetText` pour récupérer le texte d’un élément particulier.  
  
-   **CBS_LOWERCASE** : convertit en minuscules tout le texte dans le champ de sélection et la liste.  
  
-   **CBS_NOINTEGRALHEIGHT** : spécifie que la taille de la zone de liste modifiable correspond exactement à la taille spécifiée par l’application au moment de la création de la zone de liste modifiable. Généralement, Windows redimensionne une zone de liste modifiable pour qu’elle n’affiche aucun élément de manière partielle.  
  
-   **CBS_OEMCONVERT** : convertit le jeu de caractères ANSI du texte entré dans le contrôle d’édition de la zone de liste modifiable en jeu de caractères OEM, puis le reconvertit en ANSI. Cela garantit la conversion appropriée des caractères quand l’application appelle la fonction Windows `AnsiToOem` pour convertir une chaîne ANSI dans la zone de liste modifiable en caractères OEM. Ce style, particulièrement utile pour les zones de liste modifiable contenant des noms de fichiers, s’applique uniquement aux zones de liste modifiable créées avec les styles **CBS_SIMPLE** ou **CBS_DROPDOWN**  
  
-   **CBS_OWNERDRAWFIXED** : le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments de la zone de liste ont tous la même hauteur.  
  
-   **CBS_OWNERDRAWVARIABLE** : le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments de la zone de liste varient en hauteur.  
  
-   **CBS_SIMPLE** : la zone de liste est affichée en permanence. La sélection actuelle dans la zone de liste s’affiche dans le contrôle d’édition.  
  
-   **CBS_SORT** : trie automatiquement les chaînes entrées dans la zone de liste.  
  
-   **CBS_UPPERCASE** : convertit en majuscules tout le texte dans le champ de sélection et la liste.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create] (ccombobox-class.md #ccombobox__create   




