---
title: "___lc_locale_name_func | Microsoft Docs"
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
  - "___lc_locale_name_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_locale_name_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_locale_name_func"
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_locale_name_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction CRT interne.  Récupère le nom de paramètres régionaux actuel du thread.  
  
## Syntaxe  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## Valeur de retour  
 Pointeur vers une chaîne qui contient le nom de paramètres régionaux actuel du thread.  
  
## Notes  
 `___lc_locale_name_func` est une fonction CRT interne qui est utilisée par d'autres fonctions CRT pour obtenir le nom de paramètres régionaux actuel du stockage local des threads pour les données CRT.  Ces informations sont également disponibles à l'aide de la fonction [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) ou des fonctions [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Les fonctions CRT internes sont spécifiques à l'implémentation et soumises à modification à chaque nouvelle version.  Nous vous déconseillons de les utiliser dans votre code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\\src\\setlocal.h|  
  
## Voir aussi  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)