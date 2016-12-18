---
title: "_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l | Microsoft Docs"
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
  - "_ismbstrail"
  - "_ismbslead_l"
  - "_ismbslead"
  - "_ismbstrail_l"
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
  - "_ismbslead"
  - "ismbs"
  - "ismbslead_l"
  - "_ismbs"
  - "ismbstrail_l"
  - "ismbslead"
  - "_ismbstrail"
  - "_ismbstrail_l"
  - "ismbstrail"
  - "_ismbslead_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbslead (fonction)"
  - "_ismbslead_l (fonction)"
  - "_ismbstrail (fonction)"
  - "_ismbstrail_l (fonction)"
  - "ismbslead (fonction)"
  - "ismbslead_l (fonction)"
  - "ismbstrail (fonction)"
  - "ismbstrail_l (fonction)"
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue des tests contextuels pour les octets de tête et de fin des chaînes de caractères multioctets et détermine si un pointeur de sous\-chaîne pointe vers un octet de tête ou un octet de fin.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbslead(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbstrail(  
   const unsigned char *str,  
   const unsigned char *current   
);  
int _ismbslead_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
int _ismbstrail_l(  
   const unsigned char *str,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `str`  
 Pointeur indiquant le début de la chaîne ou l'octet de tête connu précédent.  
  
 `current`  
 Pointeur indiquant la position dans la chaîne à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_ismbslead` retourne \-1 si le caractère est un octet de tête et `_ismbstrail` retourne – 1 si le caractère est un octet de fin.  Si les chaînes d'entrée sont valides mais qu'elles ne correspondent ni à un octet de tête ni à un octet de fin, ces fonctions retournent zéro.  Si l'un ou l'autre des arguments a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `NULL` et définissent `errno` avec la valeur `EINVAL`.  
  
## Notes  
 `_ismbslead` et `_ismbstrail` sont plus lentes que les versions `_ismbblead` et `_ismbbtrail`, car elles prennent en compte le contexte des chaînes.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, à ceci près que pour leur comportement dépendant des paramètres régionaux, elles utilisent les paramètres régionaux qui sont passés au lieu des paramètres régionaux actifs.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_ismbslead`|\<mbctype.h\> ou \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbstrail`|\<mbctype.h\> ou \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbslead_l`|\<mbctype.h\> ou \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbstrail_l`|\<mbctype.h\> ou \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* Pour les constantes manifestes des conditions de test.  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)