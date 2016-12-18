---
title: "Erreur du compilateur C2356 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2356"
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un segment d'initialisation ne doit pas changer durant une unité de traduction  
  
 Causes possibles :  
  
-   `#pragma init_seg` précédé par un code d'initialisation de segments  
  
-   Directive `#pragma init_seg` précédée par une autre directive `#pragma init_seg`  
  
 Pour remédier à cela, déplacez le code d'initialisation de segments au début du module  Si plusieurs zones doivent être initialisées, déplacez\-les dans des modules séparés.  
  
 L'exemple suivant génère l'erreur C2356 :  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```