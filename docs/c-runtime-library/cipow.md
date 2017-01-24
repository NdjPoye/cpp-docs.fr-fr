---
title: "_CIpow | Microsoft Docs"
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
  - "_CIpow"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIpow"
  - "_CIpow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIpow (intrinsèque)"
  - "_CIpow (intrinsèque)"
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIpow
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule *x* élevé à la puissance *y* en fonction des valeurs au sommet de la pile.  
  
## Syntaxe  
  
```  
void __cdecl _CIpow();  
```  
  
## Notes  
 Cette version de la fonction `pow` a une convention d'appel spécialisée que le compilateur comprend.  La fonction accélère l'exécution car elle empêche la génération de sauvegardes et aide à l'allocation de registre.  
  
 La valeur résultante est envoyées vers le haut de la pile.  
  
## Configuration requise  
 **Platform:** x86  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)