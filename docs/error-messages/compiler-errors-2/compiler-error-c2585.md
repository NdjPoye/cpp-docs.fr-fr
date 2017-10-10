---
title: Erreur du compilateur C2585 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cb0720c7fa9cde9a735c4353bb6bf1d8714ff0fd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2585"></a>Erreur du compilateur C2585
conversion explicite vers 'type' est ambigüe  
  
 La conversion de type peut produire plusieurs résultats.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Conversion d’un type de classe ou structure basé sur l’héritage multiple. Si le type hérite de la classe de base même plusieurs fois, l’opérateur ou la fonction de conversion doit utiliser la résolution de portée (`::`) de spécifier les classes héritées à utiliser dans la conversion.  
  
2.  Un opérateur de conversion et un constructeur définis qui effectue la même conversion.
