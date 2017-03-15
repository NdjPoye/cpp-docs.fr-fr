---
title: "vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vswprintf_s_l"
  - "vsprintf_s"
  - "vswprintf_s"
  - "_vsprintf_s_l"
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
  - "vswprintf_s"
  - "vsprintf_s"
  - "_vstprintf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vstprintf_s_l (fonction)"
  - "vsprintf_s_l (fonction)"
  - "_vstprintf_s (fonction)"
  - "vswprintf_s (fonction)"
  - "vstprintf_s (fonction)"
  - "vstprintf_s_l (fonction)"
  - "vswprintf_s_l (fonction)"
  - "vsprintf_s (fonction)"
  - "_vsprintf_s_l (fonction)"
  - "texte mis en forme (C++)"
  - "_vswprintf_s_l (fonction)"
ms.assetid: 60e90518-57f0-4f1b-b732-f62a69702833
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ecrit une sortie formattée en utilisant un pointeur vers une liste d'arguments.  Il s'agit de versions de [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int vsprintf_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_s_l(  
   char *buffer,  
   size_t numberOfElements,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int vswprintf_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_s_l(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int vswprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie.  
  
 `numberOfElements`  
 Taille de `buffer` en caractères.  
  
 `format`  
 Spécification de format.  
  
 `argptr`  
 Pointeur vers la liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `vsprintf_s` et `vswprintf_s` renvoient le nombre de caractères écrits, sans le caractère null de fin, ou une valeur négative si une erreur de sortie se produit.  Si soit `buffer` est un pointeur null, soit `format` est un pointeur null, si le compte vaut 0, ou si le format de la chaine contient des caractères formant invalides, le gestionnaire de paramètres invalides est appelé comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoient \-1 et définie `errno` avec la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions prend un pointeur comme liste d'arguments, et le forme ensuite puis écrit les données dans la mémoire pointée par `buffer`.  
  
 `vswprintf_s` est conforme au Standard ISO C pour `vswprintf`, ce qui requiert le second paramètre, `count`, de type `size_t`.  
  
 Ces fonctions diffèrent des versions non sécurisés uniquement car les versions sécurisées prennent en charge les paramètres positionnels.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vstprintf_s`|`vsprintf_s`|`vsprintf_s`|`vswprintf_s`|  
|`_vstprintf_s_l`|`_vsprintf_s_l`|`_vsprintf_s_l`|`_vswprintf_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`vsprintf_s`, `_vsprintf_s_l`|\<stdio.h\> et \<stdarg.h\>|\<varargs.h\>\*|  
|`vswprintf_s`, `_vswprintf_s_l`|\<stdio.h\> ou \<wchar.h\>, et \<stdarg.h\>|\<varargs.h\>\*|  
  
 \* Requis pour la compatibilité UNIX V.  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_vsprintf_s.c  
// This program uses vsprintf_s to write to a buffer.  
// The size of the buffer is determined by _vscprintf.  
  
#include <stdlib.h>  
#include <stdarg.h>  
  
void test( char * format, ... )  
{  
   va_list args;  
   int len;  
   char * buffer;  
  
   va_start( args, format );  
   len = _vscprintf( format, args ) // _vscprintf doesn't count  
                               + 1; // terminating '\0'  
   buffer = malloc( len * sizeof(char) );  
   vsprintf_s( buffer, len, format, args );  
   puts( buffer );  
   free( buffer );  
}  
  
int main( void )  
{  
   test( "%d %c %d", 123, '<', 456 );  
   test( "%s", "This is a string" );  
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