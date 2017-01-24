---
title: "fscanf, _fscanf_l, fwscanf, _fwscanf_l | Microsoft Docs"
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
  - "fscanf"
  - "_fwscanf_l"
  - "_fscanf_l"
  - "fwscanf"
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
  - "fscanf"
  - "fwscanf"
  - "_ftscanf_l"
  - "_fwscanf_l"
  - "_ftscanf"
  - "_fscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fscanf_l (fonction)"
  - "_ftscanf (fonction)"
  - "_ftscanf_l (fonction)"
  - "_fwscanf_l (fonction)"
  - "données (CRT), lire à partir de flux"
  - "données mises en forme (C++), lire à partir de flux"
  - "fscanf (fonction)"
  - "fscanf_l (fonction)"
  - "ftscanf (fonction)"
  - "ftscanf_l (fonction)"
  - "fwscanf (fonction)"
  - "fwscanf_l (fonction)"
  - "flux (C++), lire des données mises en forme à partir de"
ms.assetid: 9004e978-6c5f-4bb2-98fd-51e5948933f2
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fscanf, _fscanf_l, fwscanf, _fwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données mises en forme à partir d'un flux.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md).  
  
## Syntaxe  
  
```  
int fscanf(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de champs qui sont correctement convertis et assignés ; la valeur de retour n'inclut pas les champs qui ont été lus mais non assignés.  La valeur de retour 0 indique qu'aucun champ n'a été assigné.  Si une erreur se produit, ou si la fin du flux de fichiers est atteinte avant la première conversion, la valeur de retour est `EOF` pour `fscanf` et `fwscanf`.  
  
 Ces fonctions valident leurs paramètres.  Si `stream` ou `format` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` et définissent `errno` avec la valeur `EINVAL`.  
  
## Notes  
 La fonction `fscanf` lit les données à partir de la position actuelle de `stream` dans les emplacements fournis par la liste d'arguments `argument` \(s'il en existe\).  Chaque `argument` doit être un pointeur vers une variable dont le type correspond à un spécificateur de type dans `format`.  `format` contrôle l'interprétation des champs d'entrée et a le même formulaire et la même fonction que l'argument `format` pour `scanf` ; consultez [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) pour une description de `format`*.*  
  
 `fwscanf` est une version à caractères larges de `fscanf` ; l'argument de format de `fwscanf` est une chaîne à caractères larges.  Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `fscanf` ne prend actuellement pas en charge la saisie à partir d'un flux d'UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ftscanf`|`fscanf`|`fscanf`|`fwscanf`|  
|`_ftscanf_l`|`_fscanf_l`|`_fscanf_l`|`_fwscanf_l`|  
  
 Pour plus d'informations, consultez [Champs de spécification de format — les fonctions scanf et wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fscanf`, `_fscanf_l`|\<stdio.h\>|  
|`fwscanf`, `_fwscanf_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fscanf.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   if( fopen_s( &stream, "fscanf.out", "w+" ) != 0 )  
      printf( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Security caution!  
      // Beware loading data from a file without confirming its size,  
      // as it may lead to a buffer overrun situation.  
  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf( stream, "%s", s );   // C4996  
      fscanf( stream, "%ld", &l ); // C4996  
  
      fscanf( stream, "%f", &fp ); // C4996  
      fscanf( stream, "%c", &c );  // C4996  
      // Note: fscanf is deprecated; consider using fscanf_s instead  
  
      // Output data read:   
      printf( "%s\n", s );  
      printf( "%ld\n", l );  
      printf( "%f\n", fp );  
      printf( "%c\n", c );  
  
      fclose( stream );  
   }  
}  
```  
  
  **a\-string**  
**65000**  
**3.141590**  
**x**   
## Équivalent .NET Framework  
 [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx). Voir également des méthodes `Parse`, telles que [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)