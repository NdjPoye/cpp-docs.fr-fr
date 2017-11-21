---
title: "2.6.1 maître construction | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bff566967749068f9792a98dc3cf2151e4df3d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="261-master-construct"></a>2.6.1 Construction master
Le **master** directive identifie une construction qui spécifie un bloc structuré qui est exécuté par le thread principal de l’équipe. La syntaxe de la **master** la directive est la suivante :  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 D’autres threads dans l’équipe n’exécutent pas le bloc structuré associé. Il n’existe aucune barrière implicite sur l’entrée ou sortie de la construction de référence.