---
title: "Classes de base | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de base"
  - "classes de base, virtuels"
  - "classes dérivées, plusieurs bases"
  - "héritage, multiples"
  - "héritage multiple, classes de base"
  - "classes de base virtuelles"
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Classes de base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le processus d'héritage crée une classe dérivée qui se compose des membres des classes de base et tous les nouveaux membres ajoutés par la classe dérivée.  Dans un héritage multiple, il est possible de construire un graphique d'héritage, où la même classe de base fait partie de plusieurs classes dérivées.  L'illustration suivante montre ce graphique.  
  
 ![Plusieurs instances d'une même classe de base](../cpp/media/vc38xn1.png "vc38XN1")  
Instances multiples d'une classe de base unique  
  
 Dans l'illustration, les représentations illustrées des composants de `CollectibleString` et de `CollectibleSortable` sont affichés.  Toutefois, la classe de base, `Collectible`, est dans `CollectibleSortableString` via le chemin d'accès `CollectibleString` et le chemin d'accès `CollectibleSortable`.  Pour éliminer cette redondance, ces classes peuvent être déclarées comme classes de base virtuelles lorsqu'elles sont héritées.  
  
 Pour plus d'informations sur la déclaration des classes de base virtuelles et la composition des objets avec classes de base virtuelles, consultez [Classes de base virtuelles](../misc/virtual-base-classes.md).  
  
## Voir aussi  
 [Vue d'ensemble des classes dérivées](../misc/overview-of-derived-classes.md)