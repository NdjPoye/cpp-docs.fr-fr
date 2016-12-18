---
title: "Suppression de tous les objets d&#39;une collection CObject | Microsoft Docs"
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
  - "CObject (classe) (collection)"
  - "CObject (classe), supprimer dans la collection"
  - "classes de collection, supprimer tous les objets"
  - "classes de collection, objets partagés"
  - "objets (C++), supprimer dans les collections"
  - "objets dans les collections CObject"
  - "objets dans les collections CObject, supprimer"
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Suppression de tous les objets d&#39;une collection CObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment supprimer tous les objets d'une collection \(sans supprimer l'objet collection lui\-même\).  
  
 Pour supprimer tous les objets dans une collection de `CObject` \(ou d'objets dérivés de `CObject`\), vous utilisez l'une des techniques d'itération décrites dans l'article [Accès à tous les membres d'une collection](../mfc/accessing-all-members-of-a-collection.md) pour supprimer chaque objet.  
  
> [!CAUTION]
>  Les objets dans les collections peuvent être partagés.  Autrement dit, la collection conserve un pointeur vers l'objet, mais d'autres parties du programme peuvent également avoir des pointeurs sur le même objet.  Vous devez alors veiller à ne pas supprimer un objet qui est partagé jusqu'à ce que toutes les parties aient fini d'utiliser l'objet.  
  
 Cet article explique comment supprimer des objets dans :  
  
-   [Une liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Un tableau.](#_core_to_delete_all_elements_in_an_array)  
  
-   [Une map](#_core_to_delete_all_elements_in_a_map)  
  
#### Pour supprimer tous les objets d'une liste de pointeurs vers CObject  
  
1.  Utilisez `GetHeadPosition` et `GetNext` pour parcourir la liste.  
  
2.  Utilisez l'opérateur **supprimer** pour supprimer chaque objet tel qu'il est trouvé dans l'itération.  
  
3.  Appelez la fonction `RemoveAll` pour supprimer tous les éléments dans la liste une fois que les objets associés à ces éléments ont été supprimés.  
  
 L'exemple suivant montre comment supprimer tous les objets d'une liste d'objets `CPerson`.  Chaque objet de la liste est un pointeur vers un objet `CPerson` qui a été initialement alloué sur le tas.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/CPP/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 Le dernier appel de fonction, `RemoveAll`, est une fonction membre de la liste qui supprime tous les éléments de la liste.  La fonction membre `RemoveAt` supprime un élément.  
  
 Notez la différence entre supprimer l'élément d'un objet et supprimer l'élément lui\-même.  Supprimer un élément de la liste supprime seulement la référence de la liste à l'objet.  L'objet existe encore en mémoire.  Lorsque vous supprimez un objet, il arrête d'exister et sa mémoire est libérée.  Par conséquent, il est important de supprimer un élément dès que l'objet de l'élément a été supprimé afin que la liste ne tente pas d'accéder aux objets qui n'existent plus.  
  
#### Pour supprimer tous les éléments d'un tableau  
  
1.  Utilisez `GetSize` et des indices entiers pour itérer au sein de le tableau.  
  
2.  Utilisez l'opérateur **supprimer** pour supprimer chaque élément tel qu'il est trouvé dans l'itération.  
  
3.  Appelez la fonction `RemoveAll` pour supprimer tous les éléments du tableau après qu'ils ont été supprimés.  
  
     Le code pour supprimer tous les éléments d'un tableau est comme suit :  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/CPP/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 Comme dans l'exemple de liste ci\-dessus, vous pouvez appeler `RemoveAll` pour supprimer tous les éléments d'un tableau ou `RemoveAt` pour supprimer un élément individuel.  
  
#### Pour supprimer tous les éléments d'une map  
  
1.  Utilisez `GetStartPosition` et `GetNextAssoc` pour parcourir le tableau.  
  
2.  Utilisez l'opérateur **supprimer** pour supprimer la clé et\/ou la valeur de chaque élément de carte tel qu'il est produit dans l'itération.  
  
3.  Appelez la fonction `RemoveAll` pour supprimer tous les éléments de la map après qu'ils ont été supprimés.  
  
     Le code pour supprimer tous les éléments d'une collection `CMap` est comme suit.  Chaque élément de la map a une chaîne comme clé et un objet `CPerson` \(dérivés de `CObject`\) comme valeur.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/CPP/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 Vous pouvez appeler `RemoveAll` pour supprimer tous les éléments d'une map ou `RemoveKey` pour supprimer un élément individuel avec la clé spécifiée.  
  
## Voir aussi  
 [Accès à tous les membres d'une collection](../mfc/accessing-all-members-of-a-collection.md)