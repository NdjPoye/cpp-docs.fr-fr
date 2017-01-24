---
title: "ToAscii, __toascii | Microsoft Docs"
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
  - "__toascii"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__toascii"
  - "toascii"
  - "ctype/toascii"
  - "ctype/__toascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "toascii (fonction)"
  - "conversion de chaînes, en caractères ASCII"
  - "__toascii (fonction)"
  - "Conversion des caractères ASCII"
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ToAscii, __toascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit des caractères ASCII 7 bits par troncation.  
  
## Syntaxe  
  
```  
int __toascii(  
   int c   
);  
#define toascii __toascii  
```  
  
#### Paramètres  
 `c`  
 Caractère à convertir.  
  
## Valeur de retour  
 `__toascii` Convertit la valeur de `c` pour le code ASCII 7 bits de plage et retourne le résultat. Aucune valeur de retour est réservée pour indiquer une erreur.  
  
## Notes  
 Le `__toascii` routine convertit le caractère donné en un caractère ASCII en tronquant aux bits de poids faible 7. Aucune transformation n’est appliquée.  
  
 Le `__toascii` routine est définie comme une macro, sauf si la macro de préprocesseur \_CTYPE\_DISABLE\_MACROS est défini. Pour la compatibilité descendante, `toascii` est défini comme macro uniquement lorsque [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) n’est pas défini ou est défini sur 0 ; sinon, il n’est pas défini.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`toascii`, `__toascii`|C: \< ctype.h \><br /><br /> C\+\+ : \< cctype \> ou \< ctype.h \>|  
  
 Le `toascii` \(macro\) est une extension POSIX, et `__toascii` est une implémentation spécifique à Microsoft de l’extension POSIX. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [is, isw, routines](../../c-runtime-library/is-isw-routines.md)   
 [to, fonctions](../../c-runtime-library/to-functions.md)