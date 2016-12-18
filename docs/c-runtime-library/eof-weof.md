---
title: "EOF, WEOF | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EOF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "EOF (fonction)"
  - "WEOF (fonction)"
  - "fin du fichier"
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EOF, WEOF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <stdio.h>  
```  
  
## Notes  
 EOF est retourné par une routine d'E\/S lorsque la fin de fichier \(ou dans certains cas, une erreur\) est rencontrée.  
  
 WEOF génère la valeur de retour, de type **wint\_t**, utilisée pour signaler la fin d'un flux de données large, ou pour rapporter une condition d'erreur.  
  
## Voir aussi  
 [putc, putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose, \_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)