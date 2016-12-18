---
title: "fgets, fgetws | Microsoft Docs"
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
  - "fgets"
  - "fgetws"
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
  - "_fgetts"
  - "fgetws"
  - "fgets"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgetts (fonction)"
  - "fgets (fonction)"
  - "fgetts (fonction)"
  - "fgetws (fonction)"
  - "flux, obtenir des chaînes de"
  - "flux, lire dans"
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgets, fgetws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une chaîne d'un flux de données.  
  
## Syntaxe  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `str`  
 Emplacement de stockage pour les données.  
  
 `n`  
 Nombre maximal de caractères à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne `str`.  `NULL` est retourné pour indiquer une erreur ou une condition de fin de fichier.  Utilisez `feof` ou `ferror` pour déterminer si une erreur s'est produite.  Si `str` ou `stream` est un pointeur null, ou si `n` est inférieur ou égal à zéro, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 La fonction `fgets` lit une chaîne de l'argument d'entrée `stream` et la stocke dans `str`.  `fgets` lit les caractères de la position actuelle du flux et incluant le premier caractère de saut de ligne, à la fin du flux, ou jusqu'à ce que le nombre de caractères soit égal à `n` – 1, selon l'événement se produisant en premier.  Le résultat enregistré dans `str` est ajouté avec un caractère NULL.  Le caractère de saut de ligne, s'il est lu, est inclus dans la chaîne.  
  
 `fgetws` est une version à caractère élargi de `fgets`.  
  
 `fgetws` lit l'argument à caractère large `str` comme une chaîne de caractères multi\-octets ou une chaîne à caractères larges selon que `stream` est ouvert en mode texte ou en mode binaire, respectivement.  Pour plus d'informations sur l'utilisation des modes texte et binaire en Unicode et stream\-I\/O multioctets, consultez [Fichier E\/S du mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md) et [E\/S de flux Unicode dans des modes texte et binaire](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fgets`|\<stdio.h\>|  
|`fgetws`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## Entrée : crt\_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### Sortie  
  
```  
Line one.  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)  
  
-   [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)