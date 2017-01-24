---
title: "_lock_file | Microsoft Docs"
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
  - "_lock_file"
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
  - "_lock_file"
  - "lock_file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lock_file (fonction)"
  - "verrouillage de fichier (C++)"
  - "lock_file (fonction)"
ms.assetid: 75c7e0e6-efff-4747-b6ed-9bcf2b0894c3
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verrouille un objet `FILE` pour garantir la cohérence pour les threads accédant à l'objet `FILE` simultanément.  
  
## Syntaxe  
  
```  
void _lock_file(  
   FILE* file  
);  
```  
  
#### Paramètres  
 `file`  
 Gestionnaire de fichier.  
  
## Notes  
 La fonction `_lock_file` verrouille l'objet `FILE` spécifié par `file`.  Le fichier sous\-jacent n'est pas verrouillé par `_lock_file`.  Utilisez [\_unlock\_file](../../c-runtime-library/reference/unlock-file.md) pour libérer le verrou sur le fichier.  Les appels à `_lock_file` et à`_unlock_file` doivent être mis en correspondance dans un thread.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lock_file`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_lock_file.c  
// This example creates multiple threads that write to standard output  
// concurrently, first with _file_lock, then without.  
  
#include <stdio.h>  
#include <process.h>// _beginthread  
#include <windows.h>// HANDLE  
  
void Task_locked( void* str )  
{  
    for( int i=0; i<1000; ++i )  
    {  
        _lock_file( stdout );  
        for( char* cp = (char*)str; *cp; ++cp )  
        {  
            _fputc_nolock( *cp, stdout );  
        }  
        _unlock_file( stdout );  
    }  
}  
  
void Task_unlocked( void* str )  
{  
    for( int i=0; i<1000; ++i )  
    {  
        for( char* cp = (char*)str; *cp; ++cp )  
        {  
            fputc( *cp, stdout );  
        }  
    }  
}  
  
int main()  
{  
    HANDLE h[3];  
    h[0] = (HANDLE)_beginthread( &Task_locked, 0, "First\n" );  
    h[1] = (HANDLE)_beginthread( &Task_locked, 0, "Second\n" );  
    h[2] = (HANDLE)_beginthread( &Task_locked, 0, "Third\n" );  
  
    WaitForMultipleObjects( 3, h, true, INFINITE );  
  
    h[0] = (HANDLE)_beginthread( &Task_unlocked, 0, "First\n" );  
    h[1] = (HANDLE)_beginthread( &Task_unlocked, 0, "Second\n" );  
    h[2] = (HANDLE)_beginthread( &Task_unlocked, 0, "Third\n" );  
  
    WaitForMultipleObjects( 3, h, true, INFINITE );  
}  
```  
  
  **...**  
**First**  
**Seconde**  
**First**  
**Seconde**  
**Troisième**  
**Seconde**  
**Troisième**  
**Seconde**  
**...**  
**FSiercsotn**  
**dF**  
**iSrescto**  
**nFdi**  
**rSsetc**  
**oFnidr**  
**sSte**  
**cFoinrds**  
**tS**  
**eFciornsdt**   
## Équivalent .NET Framework  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_unlock\_file](../../c-runtime-library/reference/unlock-file.md)