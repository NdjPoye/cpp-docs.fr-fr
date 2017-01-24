---
title: "R&#232;gles pr&#233;d&#233;finies | Microsoft Docs"
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
helpviewer_keywords: 
  - "règles, prédéfinies"
  - "programme NMAKE, règles prédéfinies"
  - "règles prédéfinies dans NMAKE"
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#232;gles pr&#233;d&#233;finies
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles d'inférence prédéfinies utilisent les macros de commandes et d'options fournies par NMAKE.  
  
|Règle|Commande|Valeur<br /><br /> par défaut|Batch<br /><br /> Règle|La plateforme nmake s'exécute sur|  
|-----------|--------------|---------------------------|---------------------|---------------------------------------|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml $\<|non|x86|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml \/c $\<|oui|x86|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml64 $\<|non|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml64 \/c $\<|oui|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.c.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|non|all|  
|.c.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|oui|all|  
|.cc.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|non|all|  
|.cc.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|oui|all|  
|.cpp.exe|$\(CPP\) $\(CPPFLAGS\) $\<|cl $\<|non|all|  
|.cpp.obj|$\(CPP\) $\(CPPFLAGS\) \/c $\<|cl \/c $\<|oui|all|  
|.cxx.exe|$\(CXX\) $\(CXXFLAGS\) $\<|cl $\<|non|all|  
|.cxx.obj|$\(CXX\) $\(CXXFLAGS\) \/c $\<|cl \/c $\<|oui|all|  
|.rc.res|$\(RC\) $\(RFLAGS\) \/r $\<|rc \/r $\<|non|all|  
  
## Voir aussi  
 [Règles d'inférence](../build/inference-rules.md)