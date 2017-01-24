---
title: "3.3.2 omp_get_wtick Function | Microsoft Docs"
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
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.2 omp_get_wtick Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' `omp_get_wtick` retourne une valeur à virgule flottante en double précision égale au nombre de secondes entre les battements d'horloge consécutifs.  Le format est comme suit :  
  
```  
#include <omp.h>  
double omp_get_wtick(void);  
```