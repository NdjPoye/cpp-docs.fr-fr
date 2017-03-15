---
title: "_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_itow"
  - "_i64tow"
  - "_itoa"
  - "_i64toa"
  - "_ui64toa"
  - "_ui64tow"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_i64tow"
  - "ui64toa"
  - "ui64tow"
  - "itot"
  - "_itot"
  - "_i64toa"
  - "_itoa"
  - "_itow"
  - "_ui64tow"
  - "i64toa"
  - "i64tow"
  - "itow"
  - "_ui64toa"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_i64toa (fonction)"
  - "_i64tow (fonction)"
  - "_itoa (fonction)"
  - "_itot (fonction)"
  - "_itow (fonction)"
  - "_ui64toa (fonction)"
  - "_ui64tow (fonction)"
  - "convertir des entiers"
  - "convertir des nombres, en chaînes"
  - "i64toa (fonction)"
  - "i64tow (fonction)"
  - "entiers, convertir"
  - "itoa (fonction)"
  - "itot (fonction)"
  - "itow (fonction)"
  - "ui64toa (fonction)"
  - "ui64tow (fonction)"
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit un entier en chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md).  
  
## Syntaxe  
  
```  
char *_itoa(  
   int value,  
   char *str,  
   int radix   
);  
char *_i64toa(  
   __int64 value,  
   char *str,  
   int radix   
);  
char * _ui64toa(  
   unsigned _int64 value,  
   char *str,  
   int radix   
);  
wchar_t * _itow(  
   int value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_itoa(  
   int value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char *_i64toa(  
   __int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char * _ui64toa(  
   unsigned _int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _itow(  
   int value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### Paramètres  
 `value`  
 Nombre devant être converti.  
  
 `str`  
 Chaîne de résultat.  
  
 `radix`  
 Base de `value`; qui doit être comprise entre 2\-36.  
  
## Valeur de retour  
 Chacune de ces fonctions renvoie un pointeur vers `str`.  Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_itoa`, `_i64toa`, et `_ui64toa` convertissent les chiffres de l'argument `value` donné à une chaîne de caractères se terminant par null et les stocke le résultat \(jusqu'à 33 caractères pour `_itoa` et 65 pour `_i64toa` et `_ui64toa`\) dans `str`.  Si `radix` est égal à 10 et `value` est négative, le premier caractère de la chaîne stockée est le signe moins \( `–` \).  `_itow`, `_i64tow`et `_ui64tow`, sont des versions à caractères larges de `_itoa`, `_i64toa`, et `_ui64toa`, respectivement.  
  
> [!IMPORTANT]
>  Pour empêcher les dépassements de mémoire tampon, assurez\-vous que la mémoire tampon de `str` est suffisamment grande pour contenir les chiffres convertis plus le caractère Null de fin et un caractère de signe.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_itot`|`_itoa`|`_itoa`|`_itow`|  
|`_i64tot`|`_i64toa`|`_i64toa`|`_i64tow`|  
|`_ui64tot`|`_ui64toa`|`_ui64toa`|`_ui64tow`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_itoa`|\<stdlib.h\>|  
|`_i64toa`|\<stdlib.h\>|  
|`_ui64toa`|\<stdlib.h\>|  
|`_itow`|\<stdlib.h\>|  
|`_i64tow`|\<stdlib.h\>|  
|`_ui64tow`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_itoa.c  
// compile with: /W3  
// This program makes use of the _itoa functions  
// in various examples.  
  
#include <string.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[65];  
   int r;  
   for( r=10; r>=2; --r )  
   {  
     _itoa( -1, buffer, r ); // C4996  
     // Note: _itoa is deprecated; consider using _itoa_s instead  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _i64toa( -1L, buffer, r ); // C4996  
     // Note: _i64toa is deprecated; consider using _i64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _ui64toa( 0xffffffffffffffffL, buffer, r ); // C4996  
     // Note: _ui64toa is deprecated; consider using _ui64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
}  
```  
  
  **base 10: \-1 \(2 caractères\)**  
**base 9: 12068657453 \(11 caractères\)**  
**base 8: 37777777777 \(11 caractères\)**  
**base 7: 211301422353 \(12 caractères\)**  
**base 6: 1550104015503 \(13 caractères\)**  
**base 5: 32244002423140 \(14 caractères\)**  
**base 4: 3333333333333333 \(16 caractères\)**  
**base 3: 102002022201221111210 \(21 caractères\)**  
**base 2: 11111111111111111111111111111111 \(32 caractères\)**  
**base 10: \-1 \(2 caractères\)**  
**base 9: 145808576354216723756 \(21 caractères\)**  
**base 8: 1777777777777777777777 \(22 caractères\)**  
**base 7: 45012021522523134134601 \(23 caractères\)**  
**base 6: 3520522010102100444244423 \(25 caractères\)**  
**base 5: 2214220303114400424121122430 \(28 caractères\)**  
**base 4: 33333333333333333333333333333333 \(32 caractères\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 caractères\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 caractères\)**  
**base 10: 18446744073709551615 \(20 caractères\)**  
**base 9: 145808576354216723756 \(21 caractères\)**  
**base 8: 1777777777777777777777 \(22 caractères\)**  
**base 7: 45012021522523134134601 \(23 caractères\)**  
**base 6: 3520522010102100444244423 \(25 caractères\)**  
**base 5: 2214220303114400424121122430 \(28 caractères\)**  
**base 4: 33333333333333333333333333333333 \(32 caractères\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 caractères\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 caractères\)**   
## Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s, \_ultow\_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)