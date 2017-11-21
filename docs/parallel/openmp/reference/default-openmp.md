---
title: "la valeur par défaut (OpenMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: default
dev_langs: C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caafb7818c32dad7b21ac7a05d10f77753c1da73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="default-openmp"></a>default (OpenMP)
Spécifie le comportement de variables non délimités dans une région parallèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Remarques  
 `shared`, qui est en vigueur si le `default` clause n’est pas spécifiée, signifie que n’importe quelle variable dans une région parallèle sera traité comme s’il a été spécifié avec la [partagé](../../../parallel/openmp/reference/shared-openmp.md) clause. `none`signifie que les variables utilisées dans une région parallèle qui ne sont pas limités par le [privé](../../../parallel/openmp/reference/private-openmp.md), [partagé](../../../parallel/openmp/reference/shared-openmp.md), [réduction](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), ou [lastprivate](../../../parallel/openmp/reference/lastprivate.md) clause entraînera une erreur du compilateur.  
  
 `default`s’applique aux directives suivantes :  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Pour plus d’informations, consultez [2.7.2.5 par défaut](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Exemple  
 Consultez [privé](../../../parallel/openmp/reference/private-openmp.md) pour obtenir un exemple d’utilisation de `default`.  
  
## <a name="see-also"></a>Voir aussi  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)