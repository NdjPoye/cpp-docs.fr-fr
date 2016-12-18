---
title: "_CrtGetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetAllocHook"
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
  - "CrtGetAllocHook"
  - "_CrtGetAllocHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtGetAllocHook (fonction)"
  - "CrtGetAllocHook (fonction)"
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtGetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la fonction d'allocation définie par le client actuel pour raccorder dans le processus d'allocation de mémoire de débogage du runtime C \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );  
```  
  
## Valeur de retour  
 Renvoie la fonction actuellement définie de raccordement d'allocation.  
  
## Notes  
 `_CrtGetAllocHook` récupère la fonction de raccordement définie par le client d'application actuelle pour le processus d'allocation de mémoire de bibliothèque de débogage du runtime C.  
  
 Pour plus d'informations sur l'utilisation d'autres fonctions runtime raccordement\- capables et écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtGetAllocHook`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetAllocHook](../../c-runtime-library/reference/crtsetallochook.md)