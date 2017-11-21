---
title: 3.1.8 fonction omp_get_dynamic | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7507a5ef177ab3415b9cde41b250337cbed1cc6c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 Fonction omp_get_dynamic
Le **omp_get_dynamic** fonction retourne une valeur différente de zéro si l’ajustement dynamique de threads est activé, sinon, retourne 0. Le format est le suivant :  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Si l’implémentation n’implémente pas l’ajustement dynamique du nombre de threads, cette fonction retourne toujours 0.  
  
## <a name="cross-references"></a>Références externes :  
  
-   Pour obtenir une description de l’ajustement de thread dynamique, consultez [Section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sur la page 39.