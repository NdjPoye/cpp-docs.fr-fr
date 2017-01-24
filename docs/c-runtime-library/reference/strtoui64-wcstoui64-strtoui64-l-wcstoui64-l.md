---
title: "_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs"
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
  - "_strtoui64"
  - "_strtoui64_l"
  - "_wcstoui64"
  - "_wcstoui64_l"
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
  - "_wcstoui64_l"
  - "strtoui64_l"
  - "wcstoui64"
  - "_wcstoui64"
  - "_strtoui64_l"
  - "strtoui64"
  - "_strtoui64"
  - "wcstoui64_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strtoui64 (fonction)"
  - "_strtoui64_l (fonction)"
  - "_wcstoui64 (fonction)"
  - "_wcstoui64_l (fonction)"
  - "conversion de chaînes, en entiers"
  - "strtoui64 (fonction)"
  - "strtoui64_l (fonction)"
  - "wcstoui64 (fonction)"
  - "wcstoui64_l (fonction)"
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en valeur non signée `__int64`.  
  
## Syntaxe  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `nptr`  
 Chaîne terminée par Null à convertir.  
  
 `endptr`  
 Pointeur vers le caractère qui arrête l'analyse.  
  
 `base`  
 Base numérique à utiliser.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_strtoui64` renvoie la valeur qui est représentée dans la chaîne `nptr`, sauf lorsque la représentation provoque un dépassement de capacité, dans ce cas, elle retourne `_UI64_MAX`. \_`strtoui64`renvoie 0 si aucune conversion ne peut être exécutée.  
  
 `_UI64_MAX` est défini dans LIMITS.H.  
  
 Si `nptr` est `NULL` ou `base` est différent de zéro et inférieurs à 2 ou supérieur à 36, `errno` a la valeur `EINVAL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 La fonction `_strtoui64`convertit `nptr` en `unsigned` `__int64`.  `_wcstoui64` est une version à caractères larges de `_strtoui64`; son argument `nptr` est une chaîne à caractères larges.  Sinon ces fonctions se comportent de façon identique.  
  
 Les deux fonctions cessent de lire la chaîne `nptr` au premier caractère qu'elles ne peuvent pas reconnaître comme faisant partie d'un nombre.  Il peut s'agir du caractère null de fin, ou il peut s'agir du premier caractère numérique supérieur ou égal à `base`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 Le paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux actuels détermine la reconnaissance des caractères de base dans `nptr`; pour plus d'informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les fonctions qui ne disposent pas du suffixe \_l utilisent les paramètres régionaux actuels `_strtoui64_l` et les suffixes`_wcstoui64_l` sont identiques aux fonctions correspondantes qui ne disposent pas du suffixe `_l`, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n'a pas la valeur `NULL`, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à l'emplacement désigné par `endptr`.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur de `nptr` est enregistrée à l'emplacement désigné par `endptr`.  
  
 `_strtoui64` attend `nptr` pour pointer vers une chaîne au format suivant:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 Un `whitespace` peut être composé de caractères espace et tabulation, qui sont ignorés ; `digits` sont un ou plusieurs chiffres décimaux.  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  Si `base` est compris entre 2 et 36, il est utilisé comme base du nombre.  Si `base` est 0, les caractères initiaux de la chaîne désignée par `nptr` sont utilisés pour déterminer la base.  Si le premier caractère est 0 et le deuxième caractère n'est pas « x » ou « X », la chaîne est interprétée comme un entier octal.  Si le premier caractère est « 0 » et le deuxième caractère est « x » ou « X », la chaîne est interprétée comme un entier hexadécimal.  Si le premier caractère est compris entre « 1 » et « 9 », la chaîne est interprétée comme un entier décimal.  Les valeurs 10 à 35 sont assignées aux lettres « à » à « z » \(ou « À » à « Z »\) ; seules les lettres dont les valeurs assignées sont inférieures à `base` sont autorisées.  Le premier caractère en dehors de la plage de la base arrête l'analyse.  Par exemple, si `base` correspond à 0 et le premier caractère analysé est « 0 », un entier octal est supposé et un caractère « 8 » ou « 9 » arrêtera l'analyse.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strtoui64`|\<stdlib.h\>|  
|`_wcstoui64`|\<stdlib.h\> ou \<wchar.h\>|  
|`_strtoui64_l`|\<stdlib.h\>|  
|`_wcstoui64_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
  **u \= 18446744073709551615**   
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)