---
title: "_get_printf_count_output | Microsoft Docs"
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
  - "_get_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_printf_count_output"
  - "_get_printf_count_output"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "%n (format)"
  - "_get_printf_count_output (fonction)"
  - "get_printf_count_output (fonction)"
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique si les fonctions de famille [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) prennent en charge le format `%n`.  
  
## Syntaxe  
  
```  
int _get_printf_count_output();  
```  
  
## Valeur de retour  
 Différent de zéro si `%n` est pris en charge, 0 si `%n` n'est pas pris en charge.  
  
## Notes  
 Si `%n` n'est pas pris en charge \(par défaut\), la rencontre de `%n` dans la chaîne de format d'une des fonctions `printf` appelle le gestionnaire de paramètre non valide comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si la prise en charge de `%n` est activée \(consultez [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)\) alors `%n` se comporte comme décrit dans [Caractères du champ de type printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple pour [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).