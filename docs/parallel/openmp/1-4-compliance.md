---
title: "1.4 conformité | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3fca67cb50cf91195d7edfb1e5e2fccfc9f8c5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="14-compliance"></a>1.4 Conformité
Une implémentation de l’API de C/C++ OpenMP est *conforme OpenMP* si il reconnaît et conserve la sémantique de tous les éléments de cette spécification, tel qu’indiqué dans les chapitres 1, 2, 3, 4, et l’annexe C. annexes A, B, D, E et F sont pour informations uniquement et ne font pas partie de la spécification. Les implémentations qui incluent uniquement un sous-ensemble de l’API ne sont pas compatibles OpenMP.  
  
 Les API C++ OpenMP C est une extension de la langue de base qui est pris en charge par une implémentation. Si la langue de base ne prend pas en charge une construction de langage ou une extension qui s’affiche dans ce document, l’implémentation de OpenMP n’est pas requise pour prendre en charge.  
  
 Toutes les fonctions de bibliothèque standard C et C++ et les fonctions intégrées (autrement dit, les fonctions dont le compilateur a connaissance spécifique) doit être thread-safe. Non synchronisé d’utilisation de fonctions de thread-safe par différents threads à l’intérieur d’une région parallèle ne produit pas un comportement non défini. Toutefois, le comportement peut être pas le même que dans une région de série. (Une fonction de génération de nombres aléatoires est un exemple.)  
  
 L’API de C/C++ OpenMP Spécifie que le comportement de certain est *défini par l’implémentation.* Une implémentation conforme de OpenMP est requise pour définir et son comportement dans ces cas de document. Consultez [annexe E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), 97, pour obtenir la liste de comportements définis par l’implémentation de la page.