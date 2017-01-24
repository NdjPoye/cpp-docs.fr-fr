---
title: "__CxxFrameHandler | Microsoft Docs"
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
  - "__CxxFrameHandler"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__CxxFrameHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__CxxFrameHandler"
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __CxxFrameHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction CRT interne.  Utilisée par la bibliothèque CRT pour gérer les frames d'exceptions structurées.  
  
## Syntaxe  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(       EHExceptionRecord  *pExcept,       EHRegistrationNode *pRN,       void               *pContext,        DispatcherContext  *pDC    )  
```  
  
#### Paramètres  
 `pExcept`  
 Enregistrement d'exception qui est transmis aux instructions `catch` possibles.  
  
 `pRN`  
 Informations dynamiques sur le frame de pile utilisé pour gérer l'exception.  Pour plus d'informations, voir ehdata.h.  
  
 `pContext`  
 Contexte.  \(Non utilisé sur les processeurs Intel.\)  
  
 `pDC`  
 Informations supplémentaires sur l'entrée de la fonction et sur le frame de pile.  
  
## Valeur de retour  
 Une des valeurs d'*expression de filtre* utilisées par [try\-except, instruction](../cpp/try-except-statement.md).  
  
## Notes  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_\_CxxFrameHandler|excpt.h, ehdata.h|