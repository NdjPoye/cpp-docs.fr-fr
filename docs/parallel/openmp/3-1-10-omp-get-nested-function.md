---
title: "3.1.10 omp_get_nested Function | Microsoft Docs"
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
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.10 omp_get_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' `omp_get_nested` retourne une valeur différente de zéro si le parallélisme imbriqué est activé et 0 s'il est désactivé.  Pour plus d'informations sur le parallélisme imbriqué, consultez la section 3.1.9 à la page 40.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Si une implémentation n'implémente pas le parallélisme imbriqué, cette fonction retourne toujours 0.