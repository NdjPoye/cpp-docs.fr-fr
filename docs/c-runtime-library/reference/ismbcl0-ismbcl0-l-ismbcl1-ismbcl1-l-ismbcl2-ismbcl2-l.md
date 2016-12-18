---
title: "_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbcl2"
  - "_ismbcl1"
  - "_ismbcl0"
  - "_ismbcl2_l"
  - "_ismbcl1_l"
  - "_ismbcl0_l"
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
  - "ismbcl0"
  - "_ismbcl1_l"
  - "_ismbcl0"
  - "ismbcl1"
  - "ismbcl0_l"
  - "_ismbcl2_l"
  - "ismbcl2"
  - "ismbcl1_l"
  - "_ismbcl1"
  - "_ismbcl0_l"
  - "_ismbcl2"
  - "ismbcl2_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcl0 (fonction)"
  - "_ismbcl0_l (fonction)"
  - "_ismbcl1 (fonction)"
  - "_ismbcl1_l (fonction)"
  - "_ismbcl2 (fonction)"
  - "_ismbcl2_l (fonction)"
  - "ismbcl0 (fonction)"
  - "ismbcl0_l (fonction)"
  - "ismbcl1 (fonction)"
  - "ismbcl1_l (fonction)"
  - "ismbcl2 (fonction)"
  - "ismbcl2_l (fonction)"
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Code Page 932 Specific functions**, en utilisant les paramètres régionaux actuels ou une catégorie spécifiée d'état de conversion de LC\_CTYPE.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces routines retourne une valeur différente de zéro si le caractère satisfait à la condition de test ou 0 dans le cas contraire.  Si `c`\<\= 255 et s'il existe une routine `_ismbb` correspondante \(par exemple, `_ismbcalnum` correspond à `_ismbbalnum`\), le résultat est la valeur de retour de la routine `_ismbb` correspondante .  
  
## Notes  
 Chacune de ces fonctions teste un caractère multioctet fourni pour un état donné.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test \(page de codes 932 uniquement\)|  
|-------------|--------------------------------------------------------|  
|`_ismbcl0`|Non kanji de JIS : 0x8140\=\<`c`\<\=0x889E.|  
|`_ismbcl0_l`|Non kanji de JIS : 0x8140\=\<`c`\<\=0x889E.|  
|`_ismbcl1`|JIS : niveau 1: 0x889F\=\<`c`\<\=0x9872.|  
|`_ismbcl1_l`|JIS : niveau 1: 0x889F\=\<`c`\<\=0x9872.|  
|`_ismbcl2`|JIS niveau\-2 : 0x989F\=\<`c`\<\=0xEAA4.|  
|`_ismbcl2_l`|JIS niveau\-2 : 0x989F\=\<`c`\<\=0xEAA4.|  
  
 Les fonctions vérifient que la valeur spécifiée `c` correspond aux conditions de test décrites au dessus, mais ne vérifient pas que  `c` est un caractère multi\-octets valide.  Si l'octet inférieur est dans des plages 0x00 – 0x3F, 0x7F, ou 0xFD – 0xFF, ces fonctions retournent une valeur différente de zéro, indiquant que le caractère remplit la condition de test.  Utilisez [\_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) pour tester si le caractère multi\-octets est défini.  
  
 **Fin du détail de la page de codes 932**  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbcl0`|\<mbstring.h\>|  
|`_ismbcl0_l`|\<mbstring.h\>|  
|`_ismbcl1`|\<mbstring.h\>|  
|`_ismbcl1_l`|\<mbstring.h\>|  
|`_ismbcl2`|\<mbstring.h\>|  
|`_ismbcl2_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)