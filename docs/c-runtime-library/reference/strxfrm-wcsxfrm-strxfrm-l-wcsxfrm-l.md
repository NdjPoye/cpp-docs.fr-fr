---
title: "strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strxfrm"
  - "_wcsxfrm_l"
  - "_strxfrm_l"
  - "wcsxfrm"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strxfrm"
  - "_tcsxfrm"
  - "wcsxfrm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strxfrm_l (fonction)"
  - "_tcsxfrm (fonction)"
  - "_wcsxfrm_l (fonction)"
  - "comparaison de chaînes (C++), transformer les chaînes"
  - "chaînes (C++), comparer des paramètres régionaux"
  - "strxfrm (fonction)"
  - "strxfrm_l (fonction)"
  - "tcsxfrm (fonction)"
  - "wcsxfrm (fonction)"
  - "wcsxfrm_l (fonction)"
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transforme une chaîne en fonction d'informations spécifiques aux paramètres régionaux.  
  
## Syntaxe  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `strDest`  
 Chaîne de destination.  
  
 `strSource`  
 Chaîne source.  
  
 `count`  
 Nombre maximal de caractères à placer dans `strDest`*.*  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne la longueur de la chaîne transformée, sans compter le caractère de fin NULL.  Si la valeur de retour est supérieure ou égale à `count`, le contenu de `strDest` est imprévisible.x  En cas d'erreur, chaque fonction définit `errno` et retourne `INT_MAX`.  Pour un caractère non valide, `errno` a la valeur `EILSEQ`.  
  
## Notes  
 La fonction `strxfrm` convertit la chaîne désignée par `strSource` dans un nouveau formulaire assemblé stocké dans `strDest`.  Pas plus de `count` caractères, y compris le caractère NULL, ne peuvent être transformés et placés dans la chaîne résultante.  La transformation s'effectue à l'aide du paramètre de catégorie `LC_COLLATE` des paramètres régionaux.  Pour plus d'informations sur `LC_COLLATE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  `strxfrm` utilise les paramètres régionaux actuels pour son comportement dépend des paramètres régionaux ; `_strxfrm_l` est identique à la différence qu'il utilise les paramètres régionaux transmis à la place des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Après la transformation, un appel à `strcmp` avec les deux chaînes transformées génère des résultats identiques à ceux d'un appel à `strcoll` appliqué aux deux chaînes d'origine.  Comme avec `strcoll` et `stricoll`, `strxfrm` gère automatiquement des chaînes de caractères multi\-octets comme approprié.  
  
 `wcsxfrm` est une version à caractères larges de `strxfrm` ; les arguments de chaîne de `wcsxfrm` sont des pointeurs à caractères larges.  Pour `wcsxfrm`, après la transformation en chaîne, un appel à `wcscmp` avec les deux chaînes transformées génère des résultats identiques à ceux d'un appel à `wcscoll` appliqué aux deux chaînes d'origine.  `wcsxfrm` et `strxfrm` se comportent sinon de manière identique.  `wcsxfrm` utilise les paramètres régionaux actuels pour son comportement dépend des paramètres régionaux ; `_wcsxfrm_l` utilise les paramètres régionaux transmis à la place des paramètres régionaux actuels.  
  
 Ces fonctions valident leurs paramètres.  Si `strSource` est un pointeur null, ou `strDest` est un pointeur null \(sauf si le compte est zéro\), ou si `count` est supérieur à `INT_MAX`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `INT_MAX`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 Dans les paramètres régionaux « C », l'ordre des caractères dans le jeu de caractères \(jeu de caractères ASCII\) est le même que l'ordre lexicographique des caractères.  Toutefois, dans d'autres paramètres régionaux, l'ordre des caractères dans le jeu de caractères peut différer de l'ordre de caractère lexicographique.  Par exemple, avec certains paramètres régionaux européens, le caractère « a » \(valeur 0x61\) précède le caractère '&\#x00E4;' \(valeur 0xE4\) dans le jeu de caractères, mais le caractère « ä » précède le caractère « a » lexicographiquement.  
  
 Dans les paramètres régionaux pour lesquels le jeu de caractères et ordre des caractères lexicographiques diffèrent, utilisez `strxfrm` sur les chaînes d'origine puis `strcmp` sur les chaînes résultantes pour produire une comparaison lexicographique de chaîne en fonction du paramètre actuel de la catégorie `LC_COLLATE` des paramètres régionaux.  Par conséquent, pour comparer deux chaînes lexicographiquement dans les paramètres régionaux ci\-dessus, utilisez `strxfrm` sur les chaînes d'origine, puis `strcmp` sur les chaînes résultantes.  Ou bien, vous pouvez utiliser `strcoll` plutôt que `strcmp` sur les chaînes d'origine.  
  
 `strxfrm` est fondamentalement un wrapper autour de [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) avec `LCMAP_SORTKEY`.  
  
 La valeur de l'expression suivante est la taille de la table nécessaire pour contenir la transformation `strxfrm` de la chaîne source :  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 Dans les paramètres régionaux « C » uniquement, `strxfrm` équivaut à ce qui suit :  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strxfrm`|\<string.h\>|  
|`wcsxfrm`|\<string.h\> ou \<wchar.h\>|  
|`_strxfrm_l`|\<string.h\>|  
|`_wcsxfrm_l`|\<string.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)