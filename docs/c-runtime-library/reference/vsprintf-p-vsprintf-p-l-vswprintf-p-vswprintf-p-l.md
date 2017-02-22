---
title: "_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vsprintf_p"
  - "_vswprintf_p"
  - "_vsprintf_p_l"
  - "_vswprintf_p_l"
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
  - "vsprintf_p"
  - "_vswprintf_p"
  - "_vstprintf_p"
  - "vswprintf_p"
  - "_vsprintf_p"
  - "vstprintf_p"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vsprintf_p (fonction)"
  - "_vsprintf_p_l (fonction)"
  - "_vstprintf_p (fonction)"
  - "_vstprintf_p_l (fonction)"
  - "_vswprintf_p (fonction)"
  - "_vswprintf_p_l (fonction)"
  - "texte mis en forme (C++)"
  - "vsprintf_p (fonction)"
  - "vsprintf_p_l (fonction)"
  - "vstprintf_p (fonction)"
  - "vstprintf_p_l (fonction)"
  - "vswprintf_p (fonction)"
  - "vswprintf_p_l (fonction)"
ms.assetid: 00821c0d-9fee-4d8a-836c-0669cfb11317
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ecrire une sortie formatée en utilsant un pointeur vers une liste d'arguments, avec la possibilité de spécifier l'ordre dans lequel les arguments sont utilisés.  
  
## Syntaxe  
  
```  
int _vsprintf_p(  
   char *buffer,  
   size_t sizeInBytes,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_p_l(  
   char *buffer,  
   size_t sizeInBytes,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int _vswprintf_p(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_p_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie.  
  
 `sizeInBytes`  
 Taille de `buffer` en caractères.  
  
 `count`  
 Nombre maximal de caractères à stocker dans la version Unicode de cette fonction.  
  
 `format`  
 Spécification de format.  
  
 `argptr`  
 Pointeur vers la liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_vsprintf_p` et `_vswprintf_p` renvoient le nombre de caractères écrits, sans le caractère null de fin, ou une valeur négative si une erreur de sortie se produit.  
  
## Notes  
 Chacune de ces fonctions prend un pointeur comme liste d'arguments, et le forme ensuite puis écrit les données dans la mémoire pointée par `buffer`.  
  
 Ces fonctions diffèrent des versions `vsprintf_s` et `vswprintf_s` uniquement car elles prennent en charge les paramètres positionnels.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 Si les paramètres de `buffer` ou d'`format` sont des pointeurs NULL, si le nombre est zéro, ou si la chaîne de format contient les caractères de mise en forme valides, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoient \-1 et définie `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vstprintf_p`|`_vsprintf_p`|`_vsprintf_p`|`_vswprintf_p`|  
|`_vstprintf_p_l`|`_vsprintf_p_l`|`_vsprintf_p_l`|`_vswprintf_p_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_vsprintf_p`, `_vsprintf_p_l`|\<stdio.h\> et \<stdarg.h\>|\<varargs.h\>\*|  
|`_vswprintf_p`, `_vswprintf_p_l`|\<stdio.h\> ou \<wchar.h\>, et \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Requis pour la compatibilité UNIX V.  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt__vsprintf_p.c  
// This program uses vsprintf_p to write to a buffer.  
// The size of the buffer is determined by _vscprintf_p.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <stdarg.h>  
  
void example( char * format, ... )  
{  
    va_list  args;  
    int      len;  
    char     *buffer = NULL;  
  
    va_start( args, format );  
  
    // _vscprintf doesn't count the   
    // null terminating string so we add 1.  
    len = _vscprintf_p( format, args ) + 1;  
  
    // Allocate memory for our buffer  
    buffer = (char*)malloc( len * sizeof(char) );  
    if (buffer)  
    {  
        _vsprintf_p( buffer, len, format, args );  
        puts( buffer );  
        free( buffer );  
    }  
}  
  
int main( void )  
{  
    // First example  
    example( "%2$d %1$c %3$d", '<', 123, 456 );  
  
    // Second example  
    example( "%s", "This is a string" );  
}  
```  
  
  **123 \< 456**  
**Il s'agit d'une chaîne.**   
## Équivalent .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)