---
title: "2.2 Conditional Compilation | Microsoft Docs"
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
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.2 Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le nom de la macro de**OPENMP** \_est défini par les implémentations OpenMP\-conformes comme *yyyymm*constant decimal, qui sera l'année et le mois de la spécification.  Cette macro ne doit pas être la rubrique de **\#define** ou de **\#undef** prétraitant la directive.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Si les fournisseurs définissent des extensions dans OpenMP, ils peuvent spécifier les macros prédéfinies supplémentaires.