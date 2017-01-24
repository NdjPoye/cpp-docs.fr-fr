---
title: "_CIcos | Microsoft Docs"
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
  - "_CIcos"
apilocation: 
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CIcos"
  - "_CIcos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CIcos (intrinsèque)"
  - "CIcos (intrinsèque)"
ms.assetid: 6fc203fb-66f3-4ead-9784-f85833c26f1b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CIcos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule le cosinus de la valeur maximale de la pile.  
  
## Syntaxe  
  
```  
void __cdecl _CIcos();  
```  
  
## Notes  
 Cette version de la fonction `cos` a une convention d'appel spécialisée que le compilateur comprend.  La fonction accélère l'exécution car elle empêche la génération de sauvegardes et aide à l'allocation de registre.  
  
 La valeur résultante est envoyées vers le haut de la pile.  
  
## Configuration requise  
 x86 de**Plateforme :**  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)