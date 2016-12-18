---
title: "_CIfmod | Microsoft Docs"
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
  - "_CIfmod"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CIfmod"
  - "CIfmod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIfmod (intrinsèque)"
  - "_CIfmod (intrinsèque)"
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIfmod
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule le reste à virgule flottante des deux premières valeurs de la pile.  
  
## Syntaxe  
  
```  
void __cdecl _CIfmod();  
```  
  
## Notes  
 Cette version de la fonction `fmod` a une convention d'appel spécialisée que le compilateur comprend.  La fonction accélère l'exécution car elle empêche la génération de sauvegardes et aide à l'allocation de registre.  
  
 La valeur résultante est envoyées vers le haut de la pile.  
  
## Configuration requise  
 x86 de**Plateforme :**  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)