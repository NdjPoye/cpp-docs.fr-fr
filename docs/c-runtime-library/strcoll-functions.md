---
title: "strcoll, fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pages de codes, utiliser pour les comparaisons de chaînes"
  - "strcoll (fonctions)"
  - "comparaison de chaînes (C++), spécifiques à la culture"
  - "chaînes (C++), comparer par page de code"
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# strcoll, fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chacune des fonctions `strcoll` et `wcscoll` compare deux chaînes selon le paramètre de catégorie `LC_COLLATE` de la page de codes locale actuellement utilisée.  Chacune des fonctions `_mbscoll` compare deux chaînes en fonction de la page de codes multioctets actuellement utilisée.  Ces fonctions `coll` doivent être utilisées pour la comparison de chaines uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre lexicographiques dans la page de codes actuelle et que cette différence est intéressante pour la comparaison de chaînes.  Utilisez les fonctions correspondantes `cmp` uniquement pour déterminer si les deux chaines sont les memes.  
  
### strcoll, fonctions  
  
|SBCS|Unicode|MBCS|Description|  
|----------|-------------|----------|-----------------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[\_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Assemble deux chaînes|  
|[\_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Assemble deux chaînes \(ne respecte pas la casse\)|  
|[\_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Compare les premiers caractères `count` de deux chaînes|  
|[\_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Compare les premiers caractères `count` de deux chaînes \(ne respecte pas la casse\)|  
  
## Notes  
 Les versions avec caractère codé sur un octet de ces fonctions \(fonctions SBCS\)\(`strcoll`, `stricoll`, `_strncoll`, et `_strnicoll`\) et `string1` et `string2` selon les paramètre de catégorie locaux `LC_COLLATE` .  Ces fonctions diffèrent des fonctions correspondantes `strcmp` car les fonctions `strcoll` utilisent les informations de page de codes locaux, qui fournissent des tables de classement.  Pour les comparaisons de chaînes dans les environnements locaux dans lesquel l'ordre du jeu de caractères et l'ordre lexicographique des caractères diffèrent, les fonctions `strcoll` doivent être utilisé au lieu des fonctions correspondantes `strcmp`.  Pour plus d'informations sur `LC_COLLATE`, consultez [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Pour certaines pages de codes ainsi que pour les jeux de caractères correspondants, l'ordre des caractères dans le jeu de caractères peut différer de l'ordre lexicographique des caractères.  Dans les paramètres régionaux « C », ce n'est pas le cas : l'ordre des caractères dans le jeu de caractères ASCII est le même que l'ordre lexicographique des caractères.  Toutefois, dans certaines pages de codes européennes, par exemple, le caractère « a » \(valeur 0x61\) précède le caractère « ä » \(valeur 0xE4\) dans le jeu de caractères, mais le caractère « ä » précède le caractère « a » lexicographiquement.  Pour réaliser une comparaison dans l'ordre lexicographique dans une telle instance, utilisez `strcoll` plutôt que `strcmp`.  Ou bien, vous pouvez utiliser `strxfrm` sur les chaînes d'origine, et ensuite `strcmp` sur les chaînes résultantes.  
  
 `strcoll`, `stricoll`, `_strncoll`, et `_strnicoll` gèrent automatiquement des chaînes de caractères multi\-octets selon la page de codes des paramètres locaux en cours de utilisation, de même que les leurs équivalents en caractères étendus \(Unicode\).  Les versions de caractères multi\-octets de \(MBCS\) de ces fonctions, toutefois, assemblent des chaînes dans une base de caractère selon la page de codes multioctets actuellement utilisée.  
  
 Les fonctions `coll` assemblent les chaînes lexicographiquement pour la comparaison, tandis que les fonctions `cmp` testent simplement l'égalité de chaîne, ainsi les fonctions `coll` sont beaucoup plus lentes que les versions correspondantes `cmp`.  Par conséquent, les fonctions `coll` doivent être utilisées uniquement lorsqu'il existe une différence entre l'ordre du jeu de caractères et l'ordre des caractères lexicographiques dans la page de codes actuelle et que cette différence est intéressante pour la comparaison de chaînes.  
  
## Voir aussi  
 [Paramètres régionaux](../c-runtime-library/locale.md)   
 [Manipulation de chaînes](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)