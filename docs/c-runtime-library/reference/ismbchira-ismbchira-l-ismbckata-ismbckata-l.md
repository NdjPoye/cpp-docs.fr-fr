---
title: "_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft Docs"
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
  - "_ismbckata"
  - "_ismbchira_l"
  - "_ismbchira"
  - "_ismbckata_l"
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
  - "ismbckata_l"
  - "_ismbckata_l"
  - "ismbckata"
  - "ismbchira"
  - "_ismbckata"
  - "ismbchira_l"
  - "_ismbchira_l"
  - "_ismbchira"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbchira (fonction)"
  - "_ismbchira_l (fonction)"
  - "_ismbckata (fonction)"
  - "_ismbckata_l (fonction)"
  - "Hiragana"
  - "ismbchira (fonction)"
  - "ismbchira_l (fonction)"
  - "ismbckata (fonction)"
  - "ismbckata_l (fonction)"
  - "Katakana"
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Fonctions spécifiques de la page de code 932**  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbchira(  
   unsigned int c   
);  
int _ismbchira_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbckata(  
   unsigned int c   
);  
int _ismbckata_l(  
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
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test \(page de codes 932 uniquement\)|  
|-------------|--------------------------------------------------------|  
|`_ismbchira`|Hiragana de Deux octets : 0x829F\=\<`c`\<\=0x82F1.|  
|`_ismbchira_l`|Hiragana de Deux octets : 0x829F\=\<`c`\<\=0x82F1.|  
|`_ismbckata`|Katakana de deux octets : 0x8340\=\<`c`\<\=0x8396.|  
|`_ismbckata_l`|Katakana de deux octets : 0x8340\=\<`c`\<\=0x8396.|  
  
 **Fin du détail de la page de codes 932**  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbchira`|\<mbstring.h\>|  
|`_ismbchira_l`|\<mbstring.h\>|  
|`_ismbckata`|\<mbstring.h\>|  
|`_ismbckata_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)