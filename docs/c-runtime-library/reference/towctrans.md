---
title: "towctrans | Microsoft Docs"
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
  - "towctrans"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "towctrans"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "towctrans (fonction)"
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# towctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transforme un caractère.  
  
## Syntaxe  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à convertir.  
  
 `category`  
 Identificateur qui contient la valeur de retour de [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## Valeur de retour  
 Le caractère `c`, après `towctrans` a utilisé la règle de transformation dans `category`.  
  
## Notes  
 La valeur de `category` doit avoir été retournée par un appel réussi antérieure à [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Voir le `wctrans` pour obtenir un exemple qui utilise `towctrans`.  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)