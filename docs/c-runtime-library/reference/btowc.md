---
title: "btowc | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "btowc"
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
  - "btowc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "btowc (fonction)"
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# btowc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un entier représente un caractère codé sur un octet valide dans l'état de déplacement initial.  
  
## Syntaxe  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
## Valeur de retour  
 Retourne la représentation en caractères du caractère si l'entier représente un caractère codé sur un octet valide dans l'état de déplacement initial.  Retourne WEOF si l'entier est EOF ou n'est pas un caractère codé sur un octet valide dans l'état de déplacement initial.  Le résultat de cette fonction est affecté par les paramètres régionaux actuels `LC_TYPE`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`btowc`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)