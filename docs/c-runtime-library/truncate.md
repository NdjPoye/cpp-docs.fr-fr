---
title: "_TRUNCATE | Microsoft Docs"
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
  - "_TRUNCATE"
  - "TRUNCATE"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_TRUNCATE (constante)"
  - "TRUNCATE (constante)"
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _TRUNCATE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le comportement de la troncation de chaîne.  
  
## Syntaxe  
  
```  
#include <stdlib.h>  
```  
  
## Notes  
 `_TRUNCATE` active le comportement de la troncation quand il est transmis comme le paramètre `count` à ces fonctions :  
  
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 [mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)  
  
 [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)  
  
 [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
 Si la mémoire tampon de destination est trop petite pour traiter la chaîne entière, le fonctionnement normal de ces fonctions est de traiter ça comme un cas d'erreur \(consultez [Validation de paramètre](../c-runtime-library/parameter-validation.md)\).  Toutefois, si la troncation de chaîne est activée en passant `_TRUNCATE`, ces fonctions copieront uniquement autant de la chaîne que ce qui peut tenir, en laissant la mémoire tampon de destination terminée par le caractère NULL, et retourneront correctement.  
  
 Chaîne de troncation modifie les valeurs de retour des fonctions affectées.  Les fonctions suivantes retournent 0 si aucune troncation ne se produit, ou `STRUNCATE` si la troncation se produit :  
  
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 Les fonctions suivantes retournent le nombre de caractères copiés si aucune troncation ne se produit, ou \-1 si la troncation se produit \(correspondant au comportement des fonctions d'origine snprintf\) :  
  
 [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
## Exemple  
  
```  
// crt_truncate.c  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
   char src[] = "1234567890";  
   char dst[5];  
   errno_t err = strncpy_s(dst, _countof(dst), src, _TRUNCATE);  
   if ( err == STRUNCATE )  
      printf( "truncation occurred!\n" );  
   printf( "'%s'\n", dst );  
}  
```  
  
  **troncation s'est produite \!**  
**'1234'**   
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)