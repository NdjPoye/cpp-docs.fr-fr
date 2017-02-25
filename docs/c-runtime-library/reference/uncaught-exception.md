---
title: "__uncaught_exception | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__uncaught_exception"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__uncaught_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__uncaught_exception"
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __uncaught_exception
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique si une ou plusieures exceptions ont été levées, mais n'a pas encore été gérée par le bloc correspondant `catch` d'une instruction [try\-catch](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## Syntaxe  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## Valeur de retour  
 `true` depuis le temps où une exception est levée dans un bloc `try` jusqu'à ce que le bloc de correspondance `catch` soit lancé ; sinon, `false`.  
  
## Notes  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_uncaught\_exception|EH.H|  
  
## Voir aussi  
 [Instructions try, throw et catch \(C\+\+\)](../../cpp/try-throw-and-catch-statements-cpp.md)