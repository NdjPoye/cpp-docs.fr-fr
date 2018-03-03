---
title: Blocs de description | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37f095f5ae46e4b555f1d3f7996bd5f357e58ee2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="description-blocks"></a>Blocs de description
Un bloc de description est une ligne de dépendance suivie éventuellement d’un bloc de commandes :  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Une ligne de dépendance spécifie une ou plusieurs cibles et zéro ou plusieurs dépendants. Une cible doit être au début de la ligne. Séparez les cibles des dépendants par un signe deux-points ( :)) ; les espaces et les tabulations sont autorisées. Pour fractionner la ligne, utilisez une barre oblique inverse (\) après une cible ou un dépendant. Si une cible n’existe pas, possède un horodatage antérieur à celui d’un dépendant ou est un [pseudocible](../build/pseudotargets.md), NMAKE exécute les commandes. Si une dépendance est une cible ailleurs et n’existe pas ou est obsolète par rapport à ses propres dépendants, NMAKE met à jour le dépendant avant la mise à jour de la dépendance actuelle.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Cibles](../build/targets.md)  
  
 [Dépendants](../build/dependents.md)  
  
## <a name="see-also"></a>Voir aussi  
 [NMAKE, référence](../build/nmake-reference.md)