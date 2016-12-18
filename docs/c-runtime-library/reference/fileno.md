---
title: "_fileno | Microsoft Docs"
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
  - "_fileno"
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
  - "_fileno"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "descripteurs de fichiers [C++], obtenir auprès de flux"
  - "fileno, fonction"
  - "_fileno, fonction"
  - "flux, obtenir des descripteurs de fichiers"
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fileno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtenir le descripteur de fichier associé à un flux.  
  
## Syntaxe  
  
```  
int _fileno(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `_fileno` retourne le descripteur de fichier.  Aucun retour d'erreur.  Le résultat n'est pas défini si `stream` ne spécifie pas un fichier ouvert.  Si un flux de données a la valeur `NULL`, \_`fileno` invoque le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie \-1 et définit `errno` à la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et d'autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
> [!NOTE]
>  Si `stdout` ou `stderr` n'est pas associé à un flux de sortie \(par exemple, dans une application Windows sans fenêtre de console\), le descripteur du fichier retourné est \-2.  Dans les versions antérieures, le descripteur du fichier retourné est \-1.  Cette modification permet aux applications de distinguer cette condition d'une erreur.  
  
## Notes  
 La routine `_fileno` retourne le descripteur de fichier actuellement associé à `stream`.  Cette routine est implémentée comme fonction et comme macro.  Pour plus d'informations sur le choix d'implémentation consultez [Choix entre des fonctions et des macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fileno`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fileno.c  
// This program uses _fileno to obtain  
// the file descriptor for some standard C streams.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );  
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );  
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );  
}  
```  
  
  **Le descripteur de fichier pour stdin est 0**  
**Le descripteur de fichier pour stdout est 1**  
**Le descripteur de fichier pour stderr est 2**   
## Équivalent .NET Framework  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)