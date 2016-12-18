---
title: "_get_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_osfhandle"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_osfhandle"
  - "_get_osfhandle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "systèmes d’exploitation, obtenir des handles de fichiers"
  - "get_osfhandle (fonction)"
  - "_get_osfhandle (fonction)"
  - "handles de fichiers [C++], système d’exploitation"
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le descripteur de fichier du système d'exploitation associé au descripteur de fichier spécifié.  
  
## Syntaxe  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### Paramètres  
 `fd`  
 Un descripteur de fichier existant.  
  
## Valeur de retour  
 Handle de fichiers du système d'exploitation si `fd` est valide.  Sinon, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si est autorisé à l'exécution pour continuer, retourne `INVALID_HANDLE_VALUE` de cette fonction \(– 1\) et définit `errno` à `EBADF`, indiquant un descripteur de fichier valide.  
  
## Notes  
 Pour fermer un fichier ouvert avec `_get_osfhandle`, appelez `_close`.  Le descripteur sous\-jacent est également fermée par un appel à `_close`, il n'est pas nécessaire d'appeler la fonction Win32 `CloseHandle` sur le descripteur d'origine.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)