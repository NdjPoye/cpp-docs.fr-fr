---
title: "3.2.4 omp_unset_lock and omp_unset_nest_lock Functions | Microsoft Docs"
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
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2.4 omp_unset_lock and omp_unset_nest_lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions permettent de libérer la propriété d'un verrou.  Le format est comme suit :  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L'argument à chacune de ces fonctions doit indiquer une variable initialisée de verrou détenue par le thread qui exécute la fonction.  Le comportement n'est pas défini si le thread ne possède pas ce verrou.  
  
 Pour un verrou simple, la fonction d' `omp_unset_lock` libère le thread en fonction de la propriété du verrou.  
  
 Pour un verrou empilable, la fonction d' `omp_unset_nest_lock` décrémente le nombre d'imbrication, et libère le thread en fonction de la propriété du verrou si le résultat est zéro.