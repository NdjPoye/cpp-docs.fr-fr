---
title: "_scprintf, _scprintf_l, _scwprintf, _scwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_scprintf_l"
  - "_scwprintf"
  - "_scwprintf_l"
  - "_scprintf"
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
  - "scprintf"
  - "_scprintf_l"
  - "_scwprintf_l"
  - "_scprintf"
  - "scwprintf"
  - "_scwprintf"
  - "scprintf_l"
  - "_sctprintf_l"
  - "scwprintf_l"
  - "_sctprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_scprintf (fonction)"
  - "_scprintf_l (fonction)"
  - "_sctprintf (fonction)"
  - "_sctprintf_l (fonction)"
  - "_scwprintf (fonction)"
  - "_scwprintf_l (fonction)"
  - "texte mis en forme (C++)"
  - "scprintf (fonction)"
  - "scprintf_l (fonction)"
  - "sctprintf (fonction)"
  - "sctprintf_l (fonction)"
  - "scwprintf (fonction)"
  - "scwprintf_l (fonction)"
ms.assetid: ecbb0ba6-5f4c-4ce6-a64b-144ad8b5fe92
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _scprintf, _scprintf_l, _scwprintf, _scwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne le nombre de caractères dans la chaine formattée.  
  
## Syntaxe  
  
```  
int _scprintf(  
   const char *format [,  
   argument] ...   
);  
int _scprintf_l(  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _scwprintf(  
   const wchar_t *format [,  
   argument] ...   
);  
int _scwprintf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### Paramètres  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Retourne le nombre de caractères qui seraient générés si la chaîne devaient être imprimée ou envoyée dans un fichier ou dans une mémoire tampon à l'aide de codes de mise en forme spécifiés.  La valeur retournée n'inclut pas le caractère NULL terminant la chaine.  `_scwprintf` effectue la même fonction pour des caractères larges.  
  
 Si `format` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et attribuent à `errno` la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces éléments et autres codes d'erreur, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chaque `argument` \(si il y en a\) est converti selon la spécification du format correspondant `format`.  Le format se compose de caractères ordinaires et a la même forme et fonction que l'argument `format` pour [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_sctprintf`|`_scprintf`|`_scprintf`|`_scwprintf`|  
|`_sctprintf_l`|`_scprintf_l`|`_scprintf_l`|`_scwprintf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_scprintf`, `_scprintf_l`|\<stdio.h\>|  
|`_scwprintf`, `_scwprintf_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt__scprintf.c  
  
#define _USE_MATH_DEFINES  
  
#include <stdio.h>  
#include <math.h>  
#include <malloc.h>  
  
int main( void )  
{  
   int count;  
   int size;  
   char *s = NULL;  
  
   count = _scprintf( "The value of Pi is calculated to be %f.\n",  
                      M_PI);  
  
   size = count + 1; // the string will need one more char for the null terminator  
   s = malloc(sizeof(char) * size);  
   sprintf_s(s, size, "The value of Pi is calculated to be %f.\n",  
                      M_PI);  
   printf("The length of the following string will be %i.\n", count);  
   printf("%s", s);  
   free( s );  
}  
```  
  
  **La longueur des chaines suivantes sera de 46.**  
**La valeur de Pi est calculée comme étant de 3,141593.**   
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)