---
title: "_ismbbkpunct, _ismbbkpunct_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkpunct_l"
  - "_ismbbkpunct"
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
  - "ismbbkpunct_l"
  - "_ismbbkpunct_l"
  - "ismbbkpunct"
  - "_ismbbkpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbkpunct_l (fonction)"
  - "ismbbkpunct_l (fonction)"
  - "ismbbkpunct (fonction)"
  - "_ismbbkpunct (fonction)"
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _ismbbkpunct, _ismbbkpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie si un caractère multioctet est un caractère de ponctuation.  
  
## Syntaxe  
  
```  
int _ismbbkpunct(  
   unsigned int c   
);  
int _ismbbkpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_ismbbkpunct` retourne une valeur différente de zéro si l'entier `c` est un symbole de ponctuation non ASCII ou 0 dans le cas contraire. Par exemple, dans la page de codes 932 uniquement, `_ismbbkpunct` teste la présence d'une ponctuation katakana.`_ismbbkpunct` utilise les paramètres régionaux actifs pour les paramètres de caractères dépendants des paramètres régionaux.`_ismbbkpunct_l` est identique, à ceci près qu'il utilise les paramètres régionaux qui sont transmis. Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbbkpunct`|\<mbctype.h\>|  
|`_ismbbkpunct_l`|\<mbctype.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Classification d'octets](../../c-runtime-library/byte-classification.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)