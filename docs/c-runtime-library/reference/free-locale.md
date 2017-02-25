---
title: "_free_locale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_free_locale"
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
  - "__free_locale"
  - "free_locale"
  - "_free_locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__free_locale (fonction)"
  - "_free_locale (fonction)"
  - "free_locale (fonction)"
  - "paramètres régionaux, libérer"
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _free_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère un objet de paramètres régionaux.  
  
## Syntaxe  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `locale`  
 Objet de paramètres régionaux à récupérer.  
  
## Notes  
 La fonction `_free_locale` permet de libérer l'objet de paramètres régionaux retour d'un appel à `_get_current_locale` ou à `_create_locale`.  
  
 Ancien nom de cette fonction, `__free_locale` \(avec deux principaux traits de soulignement\) a été déconseillé.  
  
## Configuration requise  
  
|`Routine`|En\-tête requis|  
|---------------|---------------------|  
|`_free_locale`|\<locale.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Pas d'équivalent.  
  
## Voir aussi  
 [\_get\_current\_locale](../../c-runtime-library/reference/get-current-locale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)