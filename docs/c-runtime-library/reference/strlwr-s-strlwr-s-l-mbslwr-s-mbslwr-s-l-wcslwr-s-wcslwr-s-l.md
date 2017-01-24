---
title: "_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l | Microsoft Docs"
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
  - "_strlwr_s_l"
  - "_mbslwr_s_l"
  - "_mbslwr_s"
  - "_wcslwr_s"
  - "_strlwr_s"
  - "_wcslwr_s_l"
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
  - "_strlwr_s_l"
  - "_strlwr_s"
  - "mbslwr_s_l"
  - "strlwr_s_l"
  - "_wcslwr_s"
  - "strlwr_s"
  - "mbslwr_s"
  - "_wcslwr_s_l"
  - "wcslwr_s_l"
  - "_tcslwr_s"
  - "_tcslwr_s_l"
  - "_mbslwr_s_l"
  - "wcslwr_s"
  - "_mbslwr_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbslwr_s (fonction)"
  - "_mbslwr_s_l (fonction)"
  - "_strlwr_s (fonction)"
  - "_strlwr_s_l (fonction)"
  - "_tcslwr_s (fonction)"
  - "_tcslwr_s_l (fonction)"
  - "_wcslwr_s (fonction)"
  - "_wcslwr_s_l (fonction)"
  - "casse, convertir"
  - "convertir la casse, CRT (fonctions)"
  - "mbslwr_s (fonction)"
  - "mbslwr_s_l (fonction)"
  - "conversion de chaînes (C++), casse"
  - "chaînes (C++), casse"
  - "chaînes (C++), convertir la casse"
  - "strlwr_s (fonction)"
  - "strlwr_s_l (fonction)"
  - "tcslwr_s (fonction)"
  - "tcslwr_s_l (fonction)"
  - "wcslwr_s (fonction)"
  - "wcslwr_s_l (fonction)"
ms.assetid: 4883d31b-bdac-4049-83a1-91dfdeceee79
caps.latest.revision: 42
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en minuscules, en utilisant les paramètres régionaux actuels ou un objet de paramètres régionaux qui est passé.  Ces versions [\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbslwr_s` et `_mbslwr_s_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _strlwr_s(  
   char *str,  
   size_t numberOfElements  
);  
errno_t _strlwr_s_l(  
   char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _mbslwr_s(  
   unsigned char *str,  
   size_t numberOfElements  
);  
errno_t _mbslwr_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _wcslwr_s(  
   wchar_t *str,  
   size_t numberOfElements  
);  
errno_t _wcslwr_s_l(  
   wchar_t *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _strlwr_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _strlwr_s_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbslwr_s(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _mbslwr_s_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _wcslwr_s(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wcslwr_s_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne de caractères terminée par le caractère NULL à convertir en minuscules.  
  
 `numberOfElements`  
 Taille de la mémoire tampon.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur non nul en cas d'échec.  
  
 Ces fonctions valident leurs paramètres.  Si `str` n'est pas une chaîne de caractères valide terminée par le caractère NULL, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, les fonctions retournent \-1 `EINVAL` et attribuent à `errno` la valeur `EINVAL`.  Si `numberOfElements` est inférieure à la longueur de la chaîne de caractère, les fonctions retournent également `EINVAL` et attribuent à `errno` la valeur `EINVAL`.  
  
## Notes  
 La fonction `_strlwr_s` convertit, sur place, toutes les lettres majuscules dans `str` en minuscules.  `_mbslwr_s` est une version multioctet du caractère `_strlwr_s`.`_wcslwr_s` est une version à caractère large de `_strlwr_s`.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcslwr_s`|`_strlwr_s`|`_mbslwr_s`|`_wcslwr_s`|  
|`_tcslwr_s_l`|`_strlwr_s_l`|`_mbslwr_s_l`|`_wcslwr_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strlwr_s`, `_strlwr_s_l`|\<string.h\>|  
|`_mbslwr_s`, `_mbslwr_s_l`|\<mbstring.h\>|  
|`_wcslwr_s`, `_wcslwr_s_l`|\<string.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strlwr_s.cpp  
// This program uses _strlwr_s and _strupr_s to create  
// uppercase and lowercase copies of a mixed-case string.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main()  
{  
   char str[] = "The String to End All Strings!";  
   char *copy1, *copy2;  
   errno_t err;  
  
   err = _strlwr_s( copy1 = _strdup(str), strlen(str) + 1);  
   err = _strupr_s( copy2 = _strdup(str), strlen(str) + 1);  
  
   printf( "Mixed: %s\n", str );  
   printf( "Lower: %s\n", copy1 );  
   printf( "Upper: %s\n", copy2 );  
  
   free( copy1 );  
   free( copy2 );  
  
   return 0;  
}  
```  
  
  **Mixte : La Chaîne Pour Terminer Toutes Les Chaînes \!**  
**Minuscules : la chaîne pour terminer toutes les chaînes \!**  
**Majuscule : LA CHAÎNE POUR TERMINER TOUTES LES CHAÎNES \!**   
## Équivalent .NET Framework  
 [System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)