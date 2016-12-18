---
title: "_CIexp | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CIexp"
apilocation: 
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIexp"
  - "_CIexp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIexp (intrinsèque)"
  - "_CIexp (intrinsèque)"
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIexp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule l'exponentielle de la valeur maximale sur la pile.  
  
## Syntaxe  
  
```  
void __cdecl _CIexp();  
```  
  
## Notes  
 Cette version de la fonction `exp` a une convention d'appel spécialisée que le compilateur comprend.  La fonction accélère l'exécution car elle empêche la génération de sauvegardes et aide à l'allocation de registre.  
  
 La valeur résultante est envoyées vers le haut de la pile.  
  
## Configuration requise  
 x86 de**Plateforme :**  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../c-runtime-library/reference/exp-expf.md)