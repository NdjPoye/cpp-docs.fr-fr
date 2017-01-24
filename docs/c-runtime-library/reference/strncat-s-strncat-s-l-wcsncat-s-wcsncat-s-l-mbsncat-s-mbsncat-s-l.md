---
title: "strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l | Microsoft Docs"
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
  - "_wcsncat_s_l"
  - "wcsncat_s"
  - "_mbsncat_s_l"
  - "_mbsncat_s"
  - "strncat_s"
  - "_strncat_s_l"
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
  - "strncat_s_l"
  - "_mbsncat_s_l"
  - "_tcsncat_s"
  - "wcsncat_s"
  - "wcsncat_s_l"
  - "strncat_s"
  - "_mbsncat_s"
  - "_tcsncat_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsncat_s (fonction)"
  - "_mbsncat_s_l (fonction)"
  - "_tcsncat_s (fonction)"
  - "_tcsncat_s_l (fonction)"
  - "ajouter des chaînes"
  - "concaténer des chaînes"
  - "mbsncat_s (fonction)"
  - "mbsncat_s_l (fonction)"
  - "concaténation de chaînes (C++)"
  - "chaînes (C++), ajouter"
  - "strncat_s (fonction)"
  - "strncat_s_l (fonction)"
  - "wcsncat_s (fonction)"
  - "wcsncat_s_l (fonction)"
ms.assetid: de77eca2-4d9c-4e66-abf2-a95fefc21e5a
caps.latest.revision: 42
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute des caractères à une chaîne.  Ces versions [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsncat_s` et `_mbsncat_s_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t strncat_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncat_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncat_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncat_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncat_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count  
);  
errno_t _mbsncat_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t strncat_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncat_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncat_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncat_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _mbsncat_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `strDest`  
 Chaîne cible finissant par Null.  
  
 \[in\]`numberOfElements`  
 Taille de la mémoire tampon de destination.  
  
 \[in\]`strSource`  
 Chaîne source se terminant par null.  
  
 \[in\]`count`  
 Nombre de caractères à ajouter, ou [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne zéro si l'opération a réussi, un code d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|`strDestination`|`numberOfElements`|`strSource`|Valeur de retour|Contenu de `strDestination`.|  
|----------------------|------------------------|-----------------|----------------------|----------------------------------|  
|`NULL` ou incomplet|any|any|`EINVAL`|non modifié|  
|any|any|`NULL`|`EINVAL`|non modifié|  
|any|0, ou trop petit|any|`ERANGE`|non modifié|  
  
## Notes  
 Ces fonctions essayent d'ajouter les premiers caractères `D` de `strSource` à la fin de `strDest`, où `D` est le plus petit de `count` et la longueur de `strSource`.  Si l'ajout de ces caractères `D` tiendra dans `strDest` \(dont la taille est attribuée comme `numberOfElements`\) et laissera toujours la place pour une terminateur null, alors ces caractères sont ajoutés, en commençant par le caractère Null de fin d'origine de `strDest`, et un nouveau Null de fin est ajouté ; sinon, `strDest`\[0\] est défini au caractère Null et le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Il existe une exception au paragraphe ci\-dessus.  Si `count` est [\_TRUNCATE](../../c-runtime-library/truncate.md) alors le maximum de `strSource` qui tient est ajouté à `strDest` en laissant toujours la place pour ajouter Null de fin.  
  
 Par exemple :  
  
 `char dst[5];`  
  
 `strncpy_s(dst, _countof(dst), "12", 2);`  
  
 `strncat_s(dst, _countof(dst), "34567", 3);`  
  
 signifie que nous demandons à `strncat_s` d'ajouter trois caractères à deux caractères d'une mémoire tampon longue de cinq caractères ; cela ne laisserait aucun espace pour le terminateur null, par conséquent `strncat_s` sort de la chaîne et appelle le gestionnaire de paramètre non valide.  
  
 Si le comportement de troncature est nécessaire, utilisez `_TRUNCATE` ou réglez le paramètre `size` en conséquence :  
  
 `strncat_s(dst, _countof(dst), "34567", _TRUNCATE);`  
  
 ou  
  
 `strncat_s(dst, _countof(dst), "34567", _countof(dst)-strlen(dst)-1);`  
  
 Dans tous les cas, la chaîne obtenue se termine par un caractère Null.  Si la copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 Si `strSource` ou `strDest` est `NULL`, ou est `numberOfElements` est zéro , le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à continuer, la fonction retourne `EINVAL` sans modifier ses paramètres.  
  
 `wcsncat_s` et `_mbsncat_s` sont des versions à caractères élargis et à caractères multi\-octets de `strncat_s`.  Les arguments qui sont des chaînes et la valeur de retour de `wcsncat_s` sont des chaînes à caractères larges ; ceux de `_mbsncat_s` sont des chaînes de caractères multi\-octets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsncat_s`|`strncat_s`|`_mbsnbcat_s`|`wcsncat_s`|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
 `_strncat_s_l` et `_wcsncat_s_l` n'ont aucune dépendance de paramètres régionaux ; ils sont uniquement fournis pour `_tcsncat_s_l`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strncat_s`|\<string.h\>|  
|`wcsncat_s`|\<string.h\> ou \<wchar.h\>|  
|`_mbsncat_s`, `_mbsncat_s_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strncat_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncat_s_tester( const char * initialDest,  
                          const char * src,  
                          int count )  
{  
   char dest[10];  
   strcpy_s( dest, _countof(dest), initialDest );  
  
   printf_s( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf_s( "Appending '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf_s( "Appending %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   printf_s( "    old contents of dest: '%s'\n", dest );  
  
   errno_t err = strncat_s( dest, _countof(dest), src, count );  
  
   printf_s( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncat_s_tester( "hi ", "there", 4 );  
   strncat_s_tester( "hi ", "there", 5 );  
   strncat_s_tester( "hi ", "there", 6 );  
  
   printf_s( "\nDestination buffer too small:\n" );  
   strncat_s_tester( "hello ", "there", 4 );  
  
   printf_s( "\nTruncation examples:\n" );  
  
   errno_t err = strncat_s_tester( "hello ", "there", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncat_s_tester( "hello ", "!", _TRUNCATE );  
   printf_s( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf_s( "\nSecure template overload example:\n" );  
  
   char dest[10] = "cats and ";  
   strncat( dest, "dachshunds", 15 );  
   // With secure template overloads enabled (see #define  
   // at top of file), the preceding line is replaced by  
   //    strncat_s( dest, _countof(dest), "dachshunds", 15 );  
   // Instead of causing a buffer overrun, strncat_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncat would  
   // append "dachshunds" and overrun the dest buffer.  
   printf_s( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf_s(L"Invalid parameter handler invoked: %s\n", expression);  
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
  
  **Ajout de 4 caractères « there » à une mémoire tampon de 10 octets DEST**  
 **ancien contenu de DEST : « salut »**  
 **nouveau contenu de DEST : « salut ther »**  
**Ajout de 5 caractères « there » à une mémoire tampon de 10 octets DEST**  
 **ancien contenu de DEST : « salut »**  
 **nouveau contenu de DEST : « salut there »**  
**Ajout de 6 caractères « there » à une mémoire tampon de 10 octets DEST**  
 **ancien contenu de DEST : « salut »**  
 **nouveau contenu de DEST : « salut there »**  
**Mémoire tampon de destination trop petite :**  
**Ajout de 4 caractères « there » à une mémoire tampon de 10 octets DEST**  
 **ancien contenu de DEST : « Hello »**  
**Programme de traitement des paramètres non valide appelé : \(L " mémoire tampon est trop petite " && 0\)**  
 **nouveau contenu de la destination : ''**  
**Exemples de troncation :**  
**Ajout de « there » à la mémoire tampon de 10 octets DEST avec la sémantique de troncature.**  
 **ancien contenu de DEST : « Hello »**  
 **nouveau contenu de DEST : « Hello the »**  
 **la troncation s'est produite**  
**Ajout de '\!'  à la mémoire tampon de 10 octets DEST avec la sémantique de troncature.**  
 **ancien contenu de DEST : « Hello »**  
 **nouveau contenu de DEST : 'hello \!'**  
 **la troncation ne s'est pas produit**  
**Sécurisez l'exemple de surcharge de modèle :**  
**Programme de traitement des paramètres non valide appelé : \(L " mémoire tampon est trop petite " && 0\)**  
 **nouveau contenu de la destination : ''**   
## Équivalent .NET Framework  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)