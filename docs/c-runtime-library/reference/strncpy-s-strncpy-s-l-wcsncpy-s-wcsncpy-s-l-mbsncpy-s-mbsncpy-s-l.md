---
title: "strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l | Microsoft Docs"
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
  - "_mbsncpy_s_l"
  - "wcsncpy_s"
  - "_strncpy_s_l"
  - "strncpy_s"
  - "_mbsncpy_s"
  - "_wcsncpy_s_l"
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
  - "_tcsncpy_s"
  - "_wcsncpy_s_l"
  - "strncpy_s"
  - "_strncpy_s_l"
  - "wcsncpy_s"
  - "_tcsncpy_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcpy_s (fonction)"
  - "_mbsnbcpy_s_l (fonction)"
  - "_strncpy_s_l (fonction)"
  - "_tcsncpy_s (fonction)"
  - "_tcsncpy_s_l (fonction)"
  - "_wcsncpy_s_l (fonction)"
  - "copier des chaînes"
  - "mbsncpy_s (fonction)"
  - "mbsncpy_s_l (fonction)"
  - "chaînes (C++), copier"
  - "strncpy_s (fonction)"
  - "strncpy_s_l (fonction)"
  - "wcsncpy_s (fonction)"
  - "wcsncpy_s_l (fonction)"
ms.assetid: a971c800-94d1-4d88-92f3-a2fe236a4546
caps.latest.revision: 47
caps.handback.revision: 45
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie les caractères d'une chaîne vers une autre.  Ces versions [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsncpy_s` et `_mbsncpy_s_l` ne peuvent pas être utilisés dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t strncpy_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncpy_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncpy_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncpy_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncpy_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count   
);  
errno_t _mbsncpy_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
);  
template <size_t size>  
errno_t strncpy_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncpy_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncpy_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncpy_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `strDest`  
 Chaîne de destination.  
  
 `numberOfElements`  
 La taille,en nombre de caractères,de la chaîne destinataire.  
  
 `strSource`  
 Chaîne source.  
  
 `count`  
 Le nombre de caractères à copier, ou [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si réussite, `STRUNCATE` si la troncation s'est produite, sinon un code d'erreur.  
  
### Conditions d'erreur  
  
|`strDest`|`numberOfElements`|`strSource`|Valeur de retour|Contenu de `strDest`.|  
|---------------|------------------------|-----------------|----------------------|---------------------------|  
|`NULL`|any|any|`EINVAL`|non modifié|  
|any|any|`NULL`|`EINVAL`|`strDest`\[0\] a la valeur 0|  
|any|0|any|`EINVAL`|non modifié|  
|pas `NULL`|trop petit|any|`ERANGE`|`strDest`\[0\] a la valeur 0|  
  
## Notes  
 Ces fonctions tentent de copier les premiers caractères `D` de `strSource` vers `strDest`, où `D` est le plus petit de `count` et la longueur de `strSource`.  Si ces caractères `D` rentrent dans `strDest` \(dont la taille est définie à la valeur `numberOfElements`\) et ont toujours de la place pour un terminateur null, alors ces caractères y sont copiés et un terminateur null est ajouté en queue ; sinon, `strDest`\[0\] est réglé au caractère null et le programme de traitement des paramètres invalides est appelé, ainsi qu'il est décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Il existe une exception au paragraphe ci\-dessus.  Si `count` est `_TRUNCATE`, alors tous les éléments de `strSource` qui rentrent dans `strDest` y sont copiés tout en laissant suffusamment de place pour null qui est toujours ajoutée en queue.  
  
 Par exemple :  
  
 `char dst[5];`  
  
 `strncpy_s(dst, 5, "a long string", 5);`  
  
 signifie que nous demandons à `strncpy_s` de copier cinq caractères dans une mémoire tampon de cinq octets de long ; cela ne laisserait aucun espace pour le terminateur null, par conséquent `strncpy_s` remplit la chaîne de zéros et appelle le programme de traitement des paramètres non valide.  
  
 Si le comportement de troncation est nécessaire, utilisez `_TRUNCATE` ou \(`size` – 1\) :  
  
 `strncpy_s(dst, 5, "a long string", _TRUNCATE);`  
  
 `strncpy_s(dst, 5, "a long string", 4);`  
  
 Notez que contrairement à `strncpy`, si `count` est supérieur à la longueur de `strSource`, la chaîne de destination n'est pas rempli avec des caractères null sur toute la longueur `count`.  
  
 Le comportement de `strncpy_s` est non défini si les chaînes source et de destination se superposent.  
  
 Si `strDest` ou `strSource` est `NULL`, ou si la valeur de `numberOfElements` est 0, le programme de traitement des paramètres non valide est appelé.  Si l'exécution est autorisée à se poursuivre, la fonction retourne `EINVAL` et définit `errno` à la valeur `EINVAL`.  
  
 `wcsncpy_s` et `_mbsncpy_s` sont des versions à caractères élargis et à caractères multi\-octets de `strncpy_s`.  Les arguments et la valeur de retour de `wcsncpy_s` et de `mbsncpy_s`varient en conséquence.  Ces six fonctions se comportent sinon de façon identique.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsncpy_s`|`strncpy_s`|`_mbsnbcpy_s`|`wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
> [!NOTE]
>  \_strncpy\_s\_l, l' `_wcsncpy_s_l` et `_mbsncpy_s_l` n'ont aucune dépendance aux paramètres régionaux, ne sont fournis que pour `_tcsncpy_s_l` et ne sont pas destinés à être appelés directement.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strncpy_s`, `_strncpy_s_l`|\<string.h\>|  
|`wcsncpy_s`, `_wcsncpy_s_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbsncpy_s`, `_mbsncpy_s_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strncpy_s_1.cpp  
// compile with: /MTd  
  
// these #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncpy_s_tester( const char * src,  
                          int count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "Copying '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf( "Copying %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   errno_t err = strncpy_s( dest, _countof(dest), src, count );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncpy_s_tester( "howdy", 4 );  
   strncpy_s_tester( "howdy", 5 );  
   strncpy_s_tester( "howdy", 6 );  
  
   printf( "\nDestination buffer too small:\n" );  
   strncpy_s_tester( "Hi there!!", 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   errno_t err = strncpy_s_tester( "How do you do?", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncpy_s_tester( "Howdy.", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   strncpy( dest, "very very very long", 15 );  
   // With secure template overloads enabled (see #defines at  
   // top of file), the preceding line is replaced by  
   //    strncpy_s( dest, _countof(dest), "very very very long", 15 );  
   // Instead of causing a buffer overrun, strncpy_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncpy would  
   // copy 15 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
  **Copier 4 caractères « howdy » vers une mémoire tampon de 10 octets**  
 **nouveau contenu de la destination : « howd »**  
**Copier 5 caractères « howdy » vers une mémoire tampon de 10 octets**  
 **nouveau contenu de la destination : « howdy »**  
**Copier 6 caractères « howdy » vers une mémoire tampon de 10 octets**  
 **nouveau contenu de la destination : « howdy »**  
**Mémoire tampon de destination trop petite :**  
**Copie de 10 caractères « HI there\!\! » vers une mémoire tampon de 10 octets**  
**Programme de traitement des paramètres non valide appelé : \(L " mémoire tampon est trop petite " && 0\)**  
 **nouveau contenu de la destination : ''**  
**Exemples de troncation :**  
**Copie « How do you do? » vers une mémoire tampon de 10 octets avec la sémantique de troncation**  
 **nouveau contenu de la destination : 'How do yo'**  
 **la troncation s'est produite**  
**Copie « Howdy » vers une mémoire tampon de 10 octets avec la sémantique de troncation**  
 **nouveau contenu de la destination : « howdy »**  
 **la troncation ne s'est pas produit**  
**Sécurisez l'exemple de surcharge de modèle :**  
**Programme de traitement des paramètres non valide appelé : \(L " mémoire tampon est trop petite " && 0\)**  
 **nouveau contenu de la destination : ''**   
## Exemple  
  
```  
// crt_strncpy_s_2.c  
// contrasts strncpy and strncpy_s  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char a[20] = "test";  
   char s[20];  
  
   // simple strncpy usage:  
  
   strcpy_s( s, 20, "dogs like cats" );  
   printf( "Original string:\n   '%s'\n", s );  
  
   // Here we can't use strncpy_s since we don't   
   // want null termination  
   strncpy( s, "mice", 4 );  
   printf( "After strncpy (no null-termination):\n   '%s'\n", s );  
   strncpy( s+5, "love", 4 );  
   printf( "After strncpy into middle of string:\n   '%s'\n", s );  
  
   // If we use strncpy_s, the string is terminated   
   strncpy_s( s, _countof(s), "mice", 4 );  
   printf( "After strncpy_s (with null-termination):\n   '%s'\n", s );  
  
}  
```  
  
  **Chaîne d'origine :**  
 **'les chiens aiment les chats'**  
**Après strncpy \(aucun arrêt null\) :**  
 **'les souris aiment les chats'**  
**Après strncpy au milieu de la chaîne :**  
 **'les souris aiment les chats'**  
**Après strncpy\_s \(avec un arrêt null\) :**  
 **'souris'**   
## Équivalent .NET Framework  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [strcat\_s, wcscat\_s, \_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)