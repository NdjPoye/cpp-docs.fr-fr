---
title: Classes de base | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6b08321ffb027901683a4f85960579625ce98cc2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="base-classes"></a>Classes de base
Le processus d'héritage crée une classe dérivée qui se compose des membres des classes de base et tous les nouveaux membres ajoutés par la classe dérivée. Dans un héritage multiple, il est possible de construire un graphique d'héritage, où la même classe de base fait partie de plusieurs classes dérivées. L'illustration suivante montre ce graphique.  
  
 ![Plusieurs instances d’une classe de base](../cpp/media/vc38xn1.gif "vc38XN1")  
Instances multiples d'une classe de base unique  
  
 Dans l'illustration, les représentations illustrées des composants de `CollectibleString` et de `CollectibleSortable` sont affichés. Toutefois, la classe de base, `Collectible`, est dans `CollectibleSortableString` via le chemin d'accès `CollectibleString` et le chemin d'accès `CollectibleSortable`. Pour éliminer cette redondance, ces classes peuvent être déclarées comme classes de base virtuelles lorsqu'elles sont héritées.  
  

