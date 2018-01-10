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
ms.workload: cplusplus
ms.openlocfilehash: bd4ec73b82848efcdface781738639b05a256958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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