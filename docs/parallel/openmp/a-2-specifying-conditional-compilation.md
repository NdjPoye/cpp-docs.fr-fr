---
title: "A.2   Specifying Conditional Compilation | Microsoft Docs"
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
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.2   Specifying Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les exemples suivants illustrent l'utilisation de la compilation conditionnelle en utilisant OpenMP macro `_OPENMP` \([section 2,2](../../parallel/openmp/2-2-conditional-compilation.md) à la page 8\).  Avec la compilation d'OpenMP, la macro d' `_OPENMP` est définie.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 L'opérateur défini de préprocesseur permet plusieurs macro à tester dans une directive unique.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```