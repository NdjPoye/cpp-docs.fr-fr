---
title: "_unlock_file | Microsoft Docs"
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
  - "_unlock_file"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_unlock_file"
  - "unlock_file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_unlock_file (fonction)"
  - "fichiers (C++), déverrouiller"
  - "unlock_file (fonction)"
  - "déverrouiller les fichiers"
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _unlock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déverrouille un fichier, ce qui permet à d'autres processus d'accéder au fichier.  
  
## Syntaxe  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### Paramètres  
 `file`  
 Gestionnaire de fichier.  
  
## Notes  
 La fonction `_unlock_file` déverrouille le fichier spécifié par `file`.  Déverrouiller un fichier, permet à d'autres processus d'accéder au fichier.  Cette fonction ne doit pas être appelée à moins que`_lock_file` n'ait été appelée par ke pointeur `file`.  Appeler `_unlock_file` sur un fichier qui n'est pas verrouillé peut résulter en un interblocage.  Pour obtenir un exemple, consultez [\_lock\_file](../../c-runtime-library/reference/lock-file.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_unlock_file`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_lock\_file](../../c-runtime-library/reference/lock-file.md)