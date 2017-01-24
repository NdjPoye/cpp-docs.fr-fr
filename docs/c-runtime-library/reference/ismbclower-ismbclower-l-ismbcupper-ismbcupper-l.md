---
title: "_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbclower"
  - "_ismbclower_l"
  - "_ismbcupper_l"
  - "_ismbcupper"
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
  - "_ismbcupper"
  - "_ismbclower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclower (fonction)"
  - "_ismbclower_l (fonction)"
  - "_ismbcupper (fonction)"
  - "_ismbcupper_l (fonction)"
  - "ismbclower (fonction)"
  - "ismbclower_l (fonction)"
  - "ismbcupper (fonction)"
  - "ismbcupper_l (fonction)"
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie si un caractère multioctets est en minuscules ou majuscule.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
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
 Chacune de ces fonctions teste un caractère multioctet fourni pour un état donné.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels pour leur comportement dépendant des paramètres régionaux.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|-----------------------|----------------------------------|  
|`_ismbclower`|Lettre minuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une minuscule ASCII en anglais : 0x61\=\<`c`\<\=0x7A.|  
|`_ismbclower_l`|Lettre minuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une minuscule ASCII en anglais : 0x61\=\<`c`\<\=0x7A.|  
|`_ismbcupper`|Majuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une majuscule ASCII en anglais : 0x41\=\<`c`\<\=0x5A.|  
|`_ismbcupper_l`|Majuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une majuscule ASCII en anglais : 0x41\=\<`c`\<\=0x5A.|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ismbclower`|\<mbstring.h\>|  
|`_ismbclower_l`|\<mbstring.h\>|  
|`_ismbcupper`|\<mbstring.h\>|  
|`_ismbcupper_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
  
-   [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
-   [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [\_ismbc, routines](../../c-runtime-library/ismbc-routines.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)