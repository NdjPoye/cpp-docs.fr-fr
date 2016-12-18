---
title: "3.1.6 omp_in_parallel Function | Microsoft Docs"
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
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.6 omp_in_parallel Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d' **omp\_in\_parallel** retourne une valeur différente de zéro si elle est appelée dans l'étendue dynamique d'une région parallèle exécution en parallèle ; sinon, elle retourne 0.  Le format est comme suit :  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Cette fonction retourne une valeur différente de zéro en cas de appel d'une zone exécution en parallèle, notamment les zones imbriquées qui sont sérialisées.