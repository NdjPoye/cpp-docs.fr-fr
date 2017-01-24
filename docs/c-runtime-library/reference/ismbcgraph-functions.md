---
title: "_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l | Microsoft Docs"
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
  - "_ismbcpunct_l"
  - "_ismbcblank"
  - "_ismbcprint"
  - "_ismbcgraph_l"
  - "_ismbcblank_l"
  - "_ismbcpunct"
  - "_ismbcprint_l"
  - "_ismbcspace_l"
  - "_ismbcspace"
  - "_ismbcgraph"
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
  - "_ismbcspace"
  - "_ismbcgraph"
  - "_ismbcpunct"
  - "ismbcspace_l"
  - "ismbcgraph"
  - "_ismbcgraph_l"
  - "_ismbcprint"
  - "_ismbcspace_l"
  - "ismbcprint"
  - "ismbcgraph_l"
  - "ismbcspace"
  - "ismbcpunct"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcgraph (fonction)"
  - "_ismbcgraph_l (fonction)"
  - "_ismbcprint (fonction)"
  - "_ismbcprint_l (fonction)"
  - "_ismbcpunct (fonction)"
  - "_ismbcpunct_l (fonction)"
  - "_ismbcspace (fonction)"
  - "_ismbcspace_l (fonction)"
  - "ismbcgraph (fonction)"
  - "ismbcgraph_l (fonction)"
  - "ismbcprint (fonction)"
  - "ismbcprint_l (fonction)"
  - "ismbcpunct (fonction)"
  - "ismbcpunct_l (fonction)"
  - "ismbcspace (fonction)"
  - "ismbcspace_l (fonction)"
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si le caractère est un caractère graphique, un caractère d'affichage, un signe de ponctuation, ou un espace.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à déterminer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si le caractère satisfait à la condition de test, ou 0 dans le cas contraire.  Si `c`\<\= 255 et s'il existe une routine `_ismbb` correspondante \(par exemple, `_ismbcalnum` correspond à `_ismbbalnum`\), le résultat est la valeur de retour de la routine `_ismbb` correspondante .  
  
 Les versions de ces fonctions sont identiques, sauf celles avec le suffixe `_l` qui utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Notes  
 Chacune de ces fonctions teste un caractère multioctet fourni pour un état donné.  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|-----------------------|----------------------------------|  
|`_ismbcgraph`|Graphique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un caractère ASCII ou d'un Katakana imprimable sauf un espace blanc \( \).|  
|`_ismbcprint`|Imprimable|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un caractère ASCII ou d'un Katakana imprimable, y compris un espace blanc \( \).|  
|`_ismbcpunct`|Ponctuation|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un caractère de ponctuation ASCII ou Katakana.|  
|`_ismbcblank`|Espace ou tabulation horizontale|Retourne une valeur différente de zéro si et seulement si `c` est un espace ou un caractère de tabulation horizontale :  `c`\=0x20 ou `c`\=0x09.|  
|`_ismbcspace`|Espace blanc|Retourne une valeur différente de zéro si et seulement si `c` est un espace blanc : `c`\=0x20 ou 0x09\=\<`c`\<\=0x0D.|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbcgraph`|\<mbstring.h\>|  
|`_ismbcgraph_l`|\<mbstring.h\>|  
|`_ismbcprint`|\<mbstring.h\>|  
|`_ismbcprint_l`|\<mbstring.h\>|  
|`_ismbcpunct`|\<mbstring.h\>|  
|`_ismbcpunct_l`|\<mbstring.h\>|  
|`_ismbcblank`|\<mbstring.h\>|  
|`_ismbcblank_l`|\<mbstring.h\>|  
|`_ismbcspace`|\<mbstring.h\>|  
|`_ismbcspace_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
  
-   [System::Char::IsPunctuation](https://msdn.microsoft.com/en-us/library/system.char.ispunctuation.aspx)  
  
-   [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
-   Pour `_ismbcgraph` et `_ismbcprint`: Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)