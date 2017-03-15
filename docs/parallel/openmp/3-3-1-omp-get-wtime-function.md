---
title: "3.3.1 omp_get_wtime Function | Microsoft Docs"
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
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.1 omp_get_wtime Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' `omp_get_wtime` retourne une valeur à virgule flottante en double précision correspondant au temps horloge murale écoulé en secondes étant donné que certains « postback\) dans le passé ».  « Temps réel dans le passé » est arbitraire, mais il est garanti de ne pas changer pendant l'exécution du programme d'application.  Le format est comme suit :  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Il anticipe que la fonction sera utilisée pour mesurer les temps écoulé comme indiqué dans l'exemple suivant :  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Les temps retournés sont « des heures par thread » par ce qui est destiné qu'elles ne sont pas obligatoirement être globalement cohérentes pour tous les threads participant à une application.