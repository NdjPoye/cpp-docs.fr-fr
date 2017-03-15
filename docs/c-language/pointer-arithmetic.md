---
title: "Arithm&#233;tique sur les pointeurs | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "pointeur arithmétique"
  - "arithmétique de pointeur"
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arithm&#233;tique sur les pointeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérations d'addition impliquant un pointeur et un entier fournissent des résultats significatifs uniquement si l'opérande de pointeur adresse un membre de tableau et si la valeur entière produit un décalage dans les limites du même tableau.  Lorsque la valeur entière est convertie en décalage d'adresse, le compilateur suppose que seules les positions de mémoire de même taille figurent entre l'adresse d'origine et l'adresse plus le décalage.  
  
 Cette hypothèse est valide pour les membres de tableau.  Par définition, un tableau est une série de valeurs du même type ; ses éléments résident dans des emplacements de mémoire contigus.  Toutefois, il n'est pas garanti que le stockage pour les types autres que les éléments de tableau soient remplis par le même type d'identificateurs.  Autrement dit, des vides peuvent apparaître entre les positions de mémoire, même les positions de même type.  Par conséquent, les résultats de l'ajout ou de la soustraction des adresses de toute valeur autre que des éléments de tableau sont non définis.  
  
 De même, lorsque deux valeurs de type pointeur sont soustraites, la conversion suppose que seules des valeurs du même type, sans vides, résident entre les adresses données par les opérandes.  
  
## Voir aussi  
 [Opérateurs additifs C](../c-language/c-additive-operators.md)