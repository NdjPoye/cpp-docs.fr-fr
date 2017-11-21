---
title: 3.1.6 fonction omp_in_parallel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b72351095fd56ae6543c2ca742983eef315f2158
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 Fonction omp_in_parallel
Le **omp_in_parallel** fonction retourne une valeur différente de zéro si elle est appelée dans l’étendue dynamique d’une région parallèle s’exécutant en parallèle ; sinon, retourne 0. Le format est le suivant :  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Cette fonction retourne une valeur différente de zéro lors de l’appelé à partir d’une région s’exécutant en parallèle, notamment des zones imbriquées qui sont sérialisés.