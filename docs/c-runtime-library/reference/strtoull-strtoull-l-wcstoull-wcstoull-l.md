---
title: "strtoull, _strtoull_l, wcstoull, _wcstoull_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strtoull_l"
  - "_wcstoull_l"
  - "strtoull"
  - "wcstoull"
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
  - "_wcstoull_l"
  - "_tcstoull"
  - "_tcstoull_l"
  - "wcstoull"
  - "_strtoull_l"
  - "strtoull"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoull_l (fonction)"
  - "_tcstoull (fonction)"
  - "_tcstoull_l (fonction)"
  - "_wcstoull_l (fonction)"
  - "strtoull (fonction)"
  - "wcstoull (fonction)"
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoull, _strtoull_l, wcstoull, _wcstoull_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit des chaînes en une longue valeur entière non signée.  
  
## Syntaxe  
  
```  
unsigned long long strtoull(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long long _strtoull_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long long wcstoull(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long long _wcstoull_l(  
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
 `strtoull` retourne la valeur convertie, le cas échéant, ou `ULLONG_MAX` en cas de dépassement de capacité.  `strtoull` retourne 0 si aucune conversion ne peut être exécutée.  `wcstoull` retourne les valeurs de façon analogue à `strtoull`.  Pour les deux fonctions, `errno` a la valeur `ERANGE` en cas de surcapacité ou de sous\-capacité.  
  
 Pour plus d'informations sur les codes de retour, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Chacune de ces fonctions convertit la chaîne d'entrée `nptr` à une valeur entière `unsigned long long`.  
  
 La fonction `strtoull` arrête de lire la chaîne `nptr` au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Il peut s'agir du caractère null de fin, ou il peut s'agir du premier caractère numérique supérieur ou égal à `base`.  Le paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux détermine la reconnaissance des caractères de base dans `nptr`. Pour plus d'informations, consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  `strtoull` et `wcstoull` utilisent les paramètres régionaux ; `_strtoull_l` et `_wcstoull_l` à la place utilisent les paramètres régionaux dans lesquels est passé mais sont identiques autrement.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Si `endptr` n'a pas la valeur `NULL`, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à l'emplacement désigné par `endptr`.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur de `nptr` est enregistrée à l'emplacement désigné par `endptr`.  
  
 `wcstoull` est une version à caractères larges de `strtoull` et son argument `nptr` est une chaîne à caractères larges.  Sinon, ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcstoull`|`strtoull`|`strtoull`|`wcstoull`|  
|`_tcstoull_l`|`strtoull_l`|`_strtoull_l`|`_wcstoull_l`|  
  
 `strtoull` attend `nptr` pour pointer vers une chaîne au format suivant :  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; \[`letters`\]\]  
  
 Un `whitespace` peut se composer d'espaces et de caractères de tabulation, qui sont ignorés ; les `digits` se composent d'un ou plusieurs chiffres décimaux ; les `letters` se composent d'une ou plusieurs lettres entre « a » et « z » \(ou de « A » à « Z »\).  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  Si `base` est compris entre 2 et 36, il est utilisé comme base du nombre.  Si `base` est 0, les caractères initiaux de la chaîne qui est désignée par `nptr` sont utilisés pour déterminer la base.  Si le premier caractère est « 0 » et le deuxième caractère n'est pas « x » ou « X », la chaîne est interprétée comme un entier octal.  Si le premier caractère est « 0 » et le deuxième caractère est « x » ou « X », la chaîne est interprétée comme un entier hexadécimal.  Si le premier caractère est compris entre « 1 » et « 9 », la chaîne est interprétée comme un entier décimal.  Les valeurs 10 à 35 sont assignées aux lettres « à » à « z » \(ou « À » à « Z »\) ; seules les lettres dont les valeurs assignées sont inférieures à `base` sont autorisées.  Le premier caractère en dehors de la plage de la base arrête l'analyse.  Par exemple, si `base` correspond à 0 et le premier caractère analysé est « 0 », un entier octal est supposé et un caractère « 8 » ou « 9 » arrête l'analyse.  `strtoull` autorise un préfixe de signe plus \(`+`\) ou de signe moins \(`–`\) ; un signe moins indique que la valeur de retour est négative.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strtoull`|\<stdlib.h\>|  
|`wcstoull`|\<stdlib.h\> ou \<wchar.h\>|  
|`_strtoull_l`|\<stdlib.h\>|  
|`_wcstoull_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple de [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## Équivalent .NET Framework  
 [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Fonctions de valeur chaîne en valeur numérique](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll, \_strtoll\_l, wcstoll, \_wcstoll\_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)