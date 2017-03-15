---
title: "3.1.8 omp_get_dynamic Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.8 omp_get_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' **omp\_get\_dynamic** retourne une valeur différente de zéro si la modification dynamique des threads est activé, et retourne 0 sinon.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Si l'implémentation n'implémente pas la modification dynamique du nombre de threads, cette fonction retourne toujours 0.  
  
## Références croisées :  
  
-   Pour obtenir une description de réglage dynamique de thread, consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.