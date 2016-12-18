---
title: "Stockage et alignement de structures | Microsoft Docs"
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
  - "alignement de structures"
  - "compacter des structures"
  - "stocker des structures"
  - "stockage de structures"
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Stockage et alignement de structures
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les membres d'une structure sont stockés de manière séquentielle dans l'ordre dans lequel ils sont déclarés : le premier membre a l'adresse mémoire la plus basse et le dernier la plus élevée.  
  
 Chaque objet de données a un argument *alignment\-requirement*.  Pour les structures, la spécification est le membre le plus grand.  Un *offset* est alloué à chaque objet afin que  
  
 *offset* `%` *alignment\-requirement* `==` 0  
  
 Les champs de bits adjacents sont empaquetés dans la même unité d'allocation de 1, 2 ou 4 octets si les types intégraux sont de la même taille et si le champ de bits suivant s'insère dans l'unité d'allocation actuelle sans dépasser la limite imposée par les spécifications d'alignement courantes des champs de bits.  
  
 Pour économiser l'espace ou se conformer aux structures de données existantes, vous pouvez stocker des structures de manière plus ou moins compacte.  L'option du compilateur [\/Zp](../build/reference/zp-struct-member-alignment.md)\[*n*\] et [\#pragma pack](../preprocessor/pack.md) contrôlent la façon dont les données de la structure sont « comprimées » en mémoire.  Lorsque vous utilisez l'option \/Zp\[*n*\], où *n* est 1, 2, 4, 8 ou 16, chaque membre de la structure après le premier est enregistré sur les limites d'octets étant la spécification d'alignement du champ ou la taille de compression \(*n*\), selon celui qui est le plus petit.  Les limites d'octets exprimées comme une formule sont  
  
```  
min( n, sizeof( item ) )  
```  
  
 où *n* est la taille de compression exprimée avec l'option \/Zp\[*n*\] et l'*item* est le membre de la structure.  La taille de compression par défaut est \/Zp8.  
  
 Pour utiliser le pragma `pack` pour spécifier une compression autre que celle spécifiée sur la ligne de commande pour une structure particulière, indiquez le pragma `pack`, où la taille de compression est 1, 2, 4, 8 ou 16, avant la structure.  Pour rétablir la compression donnée sur la ligne de commande, spécifiez le pragma `pack` sans argument.  
  
 Pour le compilateur Microsoft C, la taille par défaut des champs de bits est **long**.  Les membres de la structure sont alignés sur la taille du type ou sur la taille \/Zp\[*n*\], selon celui qui est le plus petit.  La taille par défaut est 4.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Déclarations de structure](../c-language/structure-declarations.md)