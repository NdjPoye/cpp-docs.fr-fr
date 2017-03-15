---
title: "strcpy, wcscpy, _mbscpy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strcpy"
  - "wcscpy"
  - "_mbscpy"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbscpy"
  - "_ftcscpy"
  - "wcscpy"
  - "_tcscpy"
  - "strcpy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscpy (fonction)"
  - "_mbscpy (fonction)"
  - "_tcscpy (fonction)"
  - "copier des chaînes"
  - "ftcscpy (fonction)"
  - "mbscpy (fonction)"
  - "strcpy (fonction)"
  - "chaînes (C++), copier"
  - "tcscpy (fonction)"
  - "wcscpy (fonction)"
ms.assetid: f97a4f81-e9ee-4f15-888a-0fa5d7094c5a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# strcpy, wcscpy, _mbscpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie une chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md).  
  
> [!IMPORTANT]
>  `_mbscpy` ne peut pas être utilisée dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *strcpy(  
   char *strDestination,  
   const char *strSource   
);  
wchar_t *wcscpy(  
   wchar_t *strDestination,  
   const wchar_t *strSource   
);  
unsigned char *_mbscpy(  
   unsigned char *strDestination,  
   const unsigned char *strSource   
);  
template <size_t size>  
char *strcpy(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
wchar_t *wcscpy(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
unsigned char *_mbscpy(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Paramètres  
 `strDestination`  
 Chaîne de destination.  
  
 `strSource`  
 Chaîne source se terminant par null.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne la chaîne de destination.  Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
## Notes  
 La fonction `strcpy` copie `strSource`, y compris le caractère null de fin, à l'emplacement spécifié par `strDestination`.  Le comportement de `strcpy` n'est pas défini si les chaînes source et de destination se chevauchent.  
  
> [!IMPORTANT]
>  Comme `strcpy` ne vérifie pas si `strDestination` contient suffisamment d'espace avant de copier `strSource`, il s'agit d'une cause potentielle de dépassements de mémoire tampon.  Par conséquent, nous vous recommandons d'utiliser plutôt [strcpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md).  
  
 `wcscpy` et `_mbscpy` sont respectivement des versions à caractères larges et à caractères multioctets de `strcpy`.  Les arguments et la valeur de retour de `wcscpy` sont des chaînes de caractères larges ; ceux de `_mbscpy` sont des chaînes de caractères multioctets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcscpy`|`strcpy`|`_mbscpy`|`wcscpy`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strcpy`|\<string.h\>|  
|`wcscpy`|\<string.h\> ou \<wchar.h\>|  
|`_mbscpy`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strcpy.c  
// compile with: /W3  
// This program uses strcpy  
// and strcat to build a phrase.  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[80];  
  
   // If you change the previous line to  
   //   char string[20];  
   // strcpy and strcat will happily overrun the string  
   // buffer.  See the examples for strncpy and strncat  
   // for safer string handling.  
  
   strcpy( string, "Hello world from " ); // C4996  
   // Note: strcpy is deprecated; use strcpy_s instead  
   strcat( string, "strcpy " );           // C4996  
   // Note: strcat is deprecated; use strcat_s instead  
   strcat( string, "and " );              // C4996  
   strcat( string, "strcat!" );           // C4996  
   printf( "String = %s\n", string );  
}  
```  
  
  **String \= Hello world from strcpy and strcat\!**   
## Équivalent .NET Framework  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)