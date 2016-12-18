---
title: "_fread_nolock_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fread_nolock_s"
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
  - "_fread_nolock_s"
  - "stdio/_fread_nolock_s"
dev_langs: 
  - "C"
  - "C++"
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fread_nolock_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit des données à partir d’un flux de données, sans verrouiller d’autres threads. Cette version de [fread\_nolock](../../c-runtime-library/reference/fread-nolock.md) offre des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
size_t _fread_nolock_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t elementCount,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage des données.  
  
 `bufferSize`  
 Taille de la mémoire tampon de destination en octets.  
  
 `elementSize`  
 Taille de l’élément à lire en octets.  
  
 `elementCount`  
 Nombre maximal d’éléments à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Consultez [fread\_s](../../c-runtime-library/reference/fread-s.md).  
  
## Notes  
 Cette fonction est une version sans verrouillage de `fread_s`. Elle est identique à `fread_s`, sauf qu’elle n’est pas protégée contre les interférences par d’autres threads. Elle peut être plus rapide, car elle n’entraîne pas la charge liée au verrouillage des autres threads. Utilisez cette fonction uniquement dans les contextes thread\-safe, par exemple avec les applications monothread ou lorsque la portée appelante gère déjà l’isolation des threads.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fread_nolock_s`|C: \<stdio.h\>; C\+\+: \<cstdio\> ou \<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)