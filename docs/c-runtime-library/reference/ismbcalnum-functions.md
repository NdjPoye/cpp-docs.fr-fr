---
title: "_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l | Microsoft Docs"
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
  - "_ismbcalpha"
  - "_ismbcalnum"
  - "_ismbcdigit"
  - "_ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha_l"
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
  - "_ismbcdigit"
  - "ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha"
  - "ismbcalnum"
  - "ismbcdigit"
  - "ismbcalpha"
  - "_ismbcalnum_l"
  - "_ismbcalnum"
  - "ismbcdigit_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcalnum (fonction)"
  - "_ismbcalnum_l (fonction)"
  - "_ismbcalpha (fonction)"
  - "_ismbcalpha_l (fonction)"
  - "_ismbcdigit (fonction)"
  - "_ismbcdigit_l (fonction)"
  - "ismbcalnum (fonction)"
  - "ismbcalnum_l (fonction)"
  - "ismbcalpha (fonction)"
  - "ismbcalpha_l (fonction)"
  - "ismbcdigit (fonction)"
  - "ismbcdigit_l (fonction)"
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie si un caractère multioctets est un alphanumérique, alpha, ou caractère numérique.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbcalnum  
(  
   unsigned int c   
);  
int _ismbcalnum_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcalpha  
(  
   unsigned int c   
);  
int _ismbcalpha_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcdigit  
(  
   unsigned int c   
);  
int _ismbcdigit_l  
(  
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
 Chacune de ces routines retourne une valeur différente de zéro si le caractère satisfait à la condition de test ou 0 dans le cas contraire.  Si `c`\<\= 255 et s'il existe une routine `_ismbb` correspondante \(par exemple, `_ismbcalnum` correspond à `_ismbbalnum`\), le résultat est la valeur de retour de la routine correspondante `_ismbb`.  
  
## Notes  
 Chacune de ces routines teste un caractère multioctet fourni pour un état donné.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|-----------------------|----------------------------------|  
|`_ismbcalnum,_ismbcalnum_l`|Caractère alphanumérique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une lettre ASCII en anglais : Afficher des exemples pour `_ismbcdigit` et `_ismbcalpha`.|  
|`_ismbcalpha,_ismbcalpha_l`|Alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une lettre en anglais ASCII : 0x41\=\<`c`\<\=0x5A ou 0x61\=\<`c`\<\=0x7A ; ou une lettre de katakana : 0xA6\=\<`c`\<\=0xDF.|  
|`_ismbcdigit,_ismbcdigit`|Chiffre|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un chiffre ASCII : 0x30\=\<`c`\<\=0x39.|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbcalnum,_ismbcalnum_l`|\<mbstring.h\>|  
|`_ismbcalpha,_ismbcalpha_l`|\<mbstring.h\>|  
|`_ismbcdigit,_ismbcdigit_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
  
-   [System::Char::IsLetter](https://msdn.microsoft.com/en-us/library/system.char.isletter.aspx)  
  
-   [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
-   \(Non applicable à `_ismbcalnum`.\) Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)