---
title: "_CIlog10 | Microsoft Docs"
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
  - "_CIlog10"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIlog10"
  - "_CIlog10"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIlog10 (intrinsèque)"
  - "CIlog10 (intrinsèque)"
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIlog10
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Effectue une opération `log10` sur la valeur plus élevée dans la pile.  
  
## Syntaxe  
  
```  
void __cdecl _CIlog10();  
```  
  
## Notes  
 Cette version de la fonction `log10` a une convention d'appel spécialisée que le compilateur comprend.  La fonction accélère l'exécution car elle empêche la génération de sauvegardes et aide à l'allocation de registre.  
  
 La valeur résultante est envoyée vers le haut de la pile.  
  
## Configuration requise  
 **Plateforme :**x86  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)