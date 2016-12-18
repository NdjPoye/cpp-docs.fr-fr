---
title: "fgetpos | Microsoft Docs"
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
  - "fgetpos"
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
  - "fgetpos"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fgetpos (fonction)"
  - "flux, indicateur de position de fichier"
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient l'indicateur de position d'un flux de données.  
  
## Syntaxe  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### Paramètres  
 `stream`  
 Flux de données cible.  
  
 `pos`  
 Stockage de positions indicateur.  
  
## Valeur de retour  
 En cas de réussite, retourne `fgetpos`.  En cas de échec, retourne une valeur différente de zéro et définit `errno` à l'une des constantes manifestes suivantes \(définies dans STDIO.H\) : `EBADF`, c'est\-à\-dire que le flux de données spécifié n'est pas un pointeur de fichier valide ou n'est pas accessible, ou `EINVAL`, ce qui signifie que la valeur de`stream` ou la valeur de`pos` n'est pas valide, par exemple si l'un deux est un pointeur NULL.  Si`stream` ou `pos` est un pointeur `NULL` la fonction appelle le gestionnaire de paramètres non valides comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## Notes  
 La fonction `fgetpos` obtient la valeur actuelle de l'indicateur d'emplacement de fichier de l'argument indicateur de position de fichiers `stream` et les stocke dans l'objet référencé par `pos`.  La fonction `fsetpos` peut utiliser par la suite les informations stockées dans `pos` pour réinitialiser le pointeur de l'argument `stream` à sa position lorsque `fgetpos` a été appelé.  La valeur `pos` est stockée dans un format interne et est destinée à être utilisée uniquement par `fgetpos` et `fsetpos`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Entrée : crt\_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### Sortie crt\_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## Équivalent .NET Framework  
 [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)