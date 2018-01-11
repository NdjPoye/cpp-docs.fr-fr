---
title: Erreur du compilateur C2585 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2585
dev_langs: C++
helpviewer_keywords: C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>Erreur du compilateur C2585
conversion explicite vers 'type' est ambigüe  
  
 La conversion de type peut produire plusieurs résultats.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Conversion d’un type de classe ou structure basé sur l’héritage multiple. Si le type hérite de la classe de base même plusieurs fois, l’opérateur ou la fonction de conversion doit utiliser la résolution de portée (`::`) de spécifier les classes héritées à utiliser dans la conversion.  
  
2.  Un opérateur de conversion et un constructeur définis qui effectue la même conversion.