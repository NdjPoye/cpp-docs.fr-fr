---
title: "&#201;valuateur d&#39;expression, erreur CXX0064 | Microsoft Docs"
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
  - "CXX0064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0064"
  - "CXX0064"
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de définir un point d'arrêt sur la fonction membre virtuelle liée  
  
 Un point d'arrêt est défini sur une fonction membre virtuelle par l'intermédiaire d'un pointeur vers un objet, par exemple :  
  
```  
pClass->vfunc( int );  
```  
  
 Il est possible de définir un point d'arrêt sur une fonction virtuelle en entrant la classe, par exemple :  
  
```  
Class::vfunc( int );  
```  
  
 Erreur identique à CAN0064.