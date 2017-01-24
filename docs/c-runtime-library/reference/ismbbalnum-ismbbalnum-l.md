---
title: "_ismbbalnum, _ismbbalnum_l | Microsoft Docs"
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
  - "_ismbbalnum"
  - "_ismbbalnum_l"
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
  - "_ismbbalnum"
  - "ismbbalnum"
  - "_ismbbalnum_l"
  - "ismbbalnum_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbbalnum_l (fonction)"
  - "ismbbalnum (fonction)"
  - "ismbbalnum_l (fonction)"
  - "_ismbbalnum (fonction)"
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbalnum, _ismbbalnum_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un caractère multioctet spécifié est alphabétique ou numérique.  
  
## Syntaxe  
  
```  
int _ismbbalnum(  
   unsigned int c   
);  
int _ismbbalnum_l(  
   unsigned int c   
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_ismbbalnum` retourne une valeur différente de zéro si l’expression :  
  
```  
isalnum || _ismbbkalnum  
```  
  
 est différent de zéro pour `c`, ou 0 dans le cas contraire.  
  
 La version de cette fonction avec le suffixe `_l` est identique, à ceci près qu’elle utilise les paramètres régionaux passés au lieu des paramètres régionaux actuels pour son comportement dépendant des paramètres régionaux.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbbalnum`|\<mbctype.h\>|  
|`_ismbbalnum_l`|\<mbctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classification d'octets](../../c-runtime-library/byte-classification.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)