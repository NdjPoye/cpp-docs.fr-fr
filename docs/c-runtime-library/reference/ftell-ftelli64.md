---
title: "ftell, _ftelli64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64"
  - "ftell"
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
  - "_ftelli64"
  - "ftell"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftelli64 (fonction)"
  - "pointeurs de fichier (C++)"
  - "pointeurs de fichier (C++), obtenir la position actuelle"
  - "ftell (fonction)"
  - "ftelli64 (fonction)"
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# ftell, _ftelli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la position actuelle d'un pointeur de fichier.  
  
## Syntaxe  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Structure cible `FILE`.  
  
## Valeur de retour  
 `ftell` et `_ftelli64` retournent la position actuelle du fichier.  La valeur retournée par `ftell` et `_ftelli64` peut ne pas refléter le décalage d'octets physique pour les flux de données ouverts en mode texte, car le mode texte provoque la traduction des informations transportées pendant les sauts de ligne.  Utilisez `ftell` avec `fseek`ou`_ftelli64`avec`_fseeki64` pour retourner aux emplacements de fichiers correctement.  En situation d'erreur, `ftell`et `_ftelli64` appellent le gestionnaire de paramètres invalides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'execution autorisée de continuer, ces fonctions retournent – 1L et définissent `errno` comme une des deux constantes, définies dans. ERRNO.H.  La constante `EBADF` signifie que l'argument de `stream` n'est pas une valeur de pointeur de fichier ou ne fait pas référence à un fichier ouvert.  `EINVAL` signifie qu'un argument invalidevalide `stream` a été passé à la fonction.  Sur des périphériques en mesure de mener des recherchers \(tels que les terminaux et des imprimantes\), ou lorsque `stream` ne fait pas référence à un fichier ouvert, la valeur de retour est pas définie.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 Les fonctions `ftell` etd'`_ftelli64`récupèrent l'emplacement actuel du pointeur de fichier \(le cas échéant\) associé à `stream`*.* La position est exprimée comme un décalare relatif par rapport au début du flux.  
  
 Notez que lorsqu'un fichier est ouvert pour ajouter des données, la position actuelle du fichier est déterminée par la dernière opération d'E\/S, et non par lorsque l'écriture suivante se produirait.  Par exemple, si un fichier est ouvert pour un ajout et que la dernière opération est une lecture, la position du fichier correspond au point où l'opération suivante de lecture devait démarer, pas où l'écriture suivante démarre. \(Lorsqu'un fichier est ouvert pour un ajout, la position de fichier est déplacée vers fin de fichier avant toute opération d'écriture.\) Si aucune opération d'E\/S ne s'est produite dans un fichier ouvert pour un ajout, la position de fichier correspond au début du fichier.  
  
 Dans le mode text, CTRL\+Z est interprété comme un caractère de fin de fichier en entrée.  Dans les fichiers ouverts pour lecture\/écriture  `fopen`et toutes les autres routines vérifient la présence de Ctrl\+Z à la fin du fichier et le supprime si possible.  C'est réalisé grâce à une combinaison de `ftell` et `fseek` ou`_ftelli64` et `_fseeki64`, pour se déplacer dans un ficuier finissant par CTRL\+Z peut engendrer un comportement incorrect de`ftell` ou `_ftelli64` vers la fin du fichier.  
  
 Cette fonction verrouille les threads appelants pendant l'exécution et est par conséquent thread\-safe.  Pour une version non verrouillante, consultez `_ftell_nolock`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|En\-têtes facultatifs|  
|--------------|---------------------|---------------------------|  
|`ftell`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64`|\<stdio.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
  **Position après avoir tenté de lire 100 octets : 100**   
## Équivalent .NET Framework  
 [System::IO::FileStream::FileStream](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)