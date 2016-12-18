---
title: "wctomb, _wctomb_l | Microsoft Docs"
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
  - "_wctomb_l"
  - "wctomb"
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
  - "wctomb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wctomb_l (fonction)"
  - "caractères, convertir"
  - "conversion de chaînes, chaînes de caractères multioctets"
  - "conversion de chaînes, caractères larges"
  - "wctomb (fonction)"
  - "wctomb_l (fonction)"
  - "caractères larges, convertir"
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctomb, _wctomb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertis le caractère large en caractère multioctets correspondant.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md).  
  
## Syntaxe  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `mbchar`  
 L'adresse d'un caractère multioctets.  
  
 `wchar`  
 Un caractère large.  
  
## Valeur de retour  
 Si `wctomb` convertis le caractère large en un caractères multioctets, il retourne le nombre d'octets \(qui n'est jamais supérieur à `MB_CUR_MAX`\) dans le caractère large.  Si `wchar` est le caractère NULL en caractères étendus \(L'\\0'\), la fonction `wctomb` retourne 1.  Si le pointeur cible `mbchar` est NULL, `wctomb` retourne 0.  Si la conversion n'est pas possible dans les paramètres régionaux actuels, `wctomb` retourne – 1 et `errno` prends la valeur `EILSEQ`.  
  
## Notes  
 La fonction `wctomb` convertit son argument `wchar` en le caractère multioctets correspondant et stocke le résultat dans `mbchar`.  Vous pouvez appeler la fonction de n'importe quel point dans tout programme.  `wctomb` utilise les paramètres régionaux actuels pour tout comportement dépend des paramètres régionaux ; `_wctomb_l` est identique à `wctomb` à l'exception qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 `wctomb` valide ses paramètres.  Si `mbchar` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne \-1.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wctomb`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Ce programme illustre le comportement de la fonction wctcomb.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
  **Convertir un caractère large :**  
 **Caractères convertis : 1**  
 **Caractère multioctets: a**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)