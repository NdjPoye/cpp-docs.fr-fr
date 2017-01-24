---
title: "_ismbbprint, _ismbbprint_l | Microsoft Docs"
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
  - "_ismbbprint_l"
  - "_ismbbprint"
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
  - "_ismbbprint_l"
  - "_ismbbprint"
  - "ismbbprint"
  - "ismbbprint_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ismbbprint_l (fonction)"
  - "ismbbprint (fonction)"
  - "_ismbbprint (fonction)"
  - "_ismbbprint_l (fonction)"
ms.assetid: d08a061c-18a8-48f2-a75d-bff4870aec9d
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbprint, _ismbbprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un caractère multioctet spécifié est un caractère d’impression.  
  
## Syntaxe  
  
```  
int _ismbbprint(  
   unsigned int c   
);  
int _ismbbprint_l(  
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
 `_ismbbprint` retourne une valeur différente de zéro si l’expression :  
  
```  
isprint || _ismbbkprint  
```  
  
 est différente de zéro pour `c`, ou 0 dans le cas contraire.`_ismbbprint` utilise les paramètres régionaux actuels pour le comportement dépendant des paramètres régionaux.`_ismbbprint_l` est identique, excepté qu’il utilise à la place les paramètres régionaux. Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbbprint`|\<mbctype.h\>|  
|`_ismbbprint_l`|\<mbctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classification d'octets](../../c-runtime-library/byte-classification.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)