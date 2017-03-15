---
title: "_get_current_locale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_current_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_current_locale"
  - "__get_current_locale"
  - "_get_current_locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__get_current_locale (fonction)"
  - "_get_current_locale (fonction)"
  - "get_current_locale (fonction)"
  - "paramètres régionaux, obtenir des informations sur"
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _get_current_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient un objet de paramètres régionaux qui représente les paramètres régionaux actuels.  
  
## Syntaxe  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## Valeur de retour  
 Un objet de paramètres régionaux qui représente les paramètres régionaux actuels.  
  
## Notes  
 La fonction `_get_current_locale` obtient les paramètres régionaux actuellement définis pour le thread et retourne un objet de paramètres régionaux représentant les paramètres régionaux.  
  
 Ancien nom de cette fonction, `__get_current_locale` \(avec deux principaux traits de soulignement\) a été déconseillé.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Pas d'équivalent.  
  
## Voir aussi  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)