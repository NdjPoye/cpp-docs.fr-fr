---
title: "_ftell_nolock, _ftelli64_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64_nolock"
  - "_ftell_nolock"
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
  - "_ftelli64_nolock"
  - "ftelli64_nolock"
  - "ftell_nolock"
  - "_ftell_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftell_nolock (fonction)"
  - "_ftelli64_nolock (fonction)"
  - "pointeurs de fichier (C++), obtenir la position actuelle"
  - "ftell_nolock (fonction)"
  - "ftelli64_nolock (fonction)"
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _ftell_nolock, _ftelli64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la position actuelle d'un pointeur de fichier, sans verrouiller le thread.  
  
## Syntaxe  
  
```  
long _ftell_nolock(   
   FILE *stream   
);  
__int64 _ftelli64_nolock(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Ciblez la structure `FILE`.  
  
## Valeur de retour  
 Identique à `ftell` et `_ftelli64`.  Pour plus d'informations, consultez [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)**.**  
  
## Notes  
 Ces fonctions sont les versions sans verrouillage de `ftell` et de `_ftelli64`, respectivement.  Ils sont identiques à `ftell` et `_ftelli64` sauf qu'ils ne sont pas protégés des interférences avec d'autres threads.  Ces fonctions peuvent être plus rapides, car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-tête facultatif|  
|--------------|---------------------|-------------------------|  
|`ftell_nolock`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64_nolock`|\<stdio.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)