---
title: "___lc_codepage_func | Microsoft Docs"
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
  - "___lc_codepage_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lc_codepage_func"
  - "___lc_codepage_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_codepage_func"
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_codepage_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction CRT interne.  Récupère la page de code active du thread.  
  
## Syntaxe  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## Valeur de retour  
 Page de code active du thread.  
  
## Notes  
 `___lc_codepage_func` est une fonction CRT interne utilisée par d'autres fonctions CRT pour obtenir la page de code active à partir du stockage local des threads pour les données CRT.  Ces informations sont aussi accessible via la fonction [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md).  
  
 Une *page de code* est le mappage de codes sur un ou deux octets en caractères individuels.  Les différentes pages de code incluent des caractères spéciaux différents, généralement personnalisés pour une langue ou un groupe de langues.  Pour plus d'informations sur les pages de code, consultez [Pages de codes](../c-runtime-library/code-pages.md).  
  
 Les fonctions CRT internes sont spécifiques à l'implémentation et sont susceptibles d'être modifiées à chaque nouvelle version.  Nous vous déconseillons de les utiliser dans votre code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`___lc_codepage_func`|crt\\src\\setlocal.h|  
  
## Voir aussi  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)