---
title: "_CxxThrowException | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CxxThrowException"
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
  - "CxxThrowException"
  - "_CxxThrowException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CxxThrowException (fonction)"
  - "CxxThrowException (fonction)"
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _CxxThrowException
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Établit l'enregistrement d'exception et appelle l'environnement d'exécution pour démarrer le traitement de l'exception.  
  
## Syntaxe  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### Paramètres  
 \[in\] `pExceptionObject`  
 L'objet qui a généré l'exception.  
  
 \[in\] `pThrowInfo`  
 Les informations nécessaires pour traiter l'exception.  
  
## Notes  
 Cette méthode est incluse dans un fichier réservé au compilateur que le compilateur utilise pour traiter des exceptions.  N'appelez pas directement la méthode  à partir du code.  
  
## Configuration requise  
 **Source :** Throw.cpp  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)