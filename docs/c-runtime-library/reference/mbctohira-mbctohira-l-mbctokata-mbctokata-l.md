---
title: "_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbctohira"
  - "_mbctohira_l"
  - "_mbctokata"
  - "_mbctokata_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_mbctokata"
  - "mbctohira"
  - "_mbctohira"
  - "_mbctohira_l"
  - "mbctokata"
  - "mbctokata_l"
  - "mbctohira_l"
  - "_mbctokata_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbctohira (fonction)"
  - "_mbctohira_l (fonction)"
  - "_mbctokata (fonction)"
  - "_mbctokata_l (fonction)"
  - "mbctohira (fonction)"
  - "mbctohira_l (fonction)"
  - "mbctokata (fonction)"
  - "mbctokata_l (fonction)"
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit des caractères Hiragana en caractères Katakana et inversement  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned int _mbctohira(  
   unsigned int c   
);  
unsigned int _mbctohira_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbctokata(  
   unsigned int c   
);  
unsigned int _mbctokata_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère multioctet à convertir.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le caractère converti `c`, si possible.  Sinon, elle retourne le caractère `c` inchangé.  
  
## Notes  
 Les fonctions `_mbctohira` et `_mbctokata` testent un caractère `c` et, dans la mesure du possible, appliquent l'une des conversions suivantes.  
  
|Routines|Conversion|  
|--------------|----------------|  
|`_mbctohira,_mbctohira_l`|Katakana multioctet en hiragana multioctet.|  
|`_mbctokata,_mbctokata_l`|Hiragana multioctet en katakana multioctet.|  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sont identiques, à ceci près que celles qui n'ont pas le suffixe `_l` utilisent les paramètres régionaux actifs pour ce comportement dépendant de ces paramètres, et celles qui ont le suffixe `_l` utilisent plutôt les paramètres régionaux qui sont passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Dans les versions antérieures, `_mbctohira` était nommé `jtohira` et `_mbctokata` s'appelait `jtokata`.  Pour le nouveau code, utilisez les nouveaux noms.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbctohira`|\<mbstring.h\>|  
|`_mbctohira_l`|\<mbstring.h\>|  
|`_mbctokata`|\<mbstring.h\>|  
|`_mbctokata_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)