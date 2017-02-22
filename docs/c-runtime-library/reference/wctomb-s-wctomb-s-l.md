---
title: "wctomb_s, _wctomb_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_s_l"
  - "wctomb_s"
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
  - "wctomb_s"
  - "_wctomb_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_s_l (fonction)"
  - "caractères, convertir"
  - "conversion de chaînes, chaînes de caractères multioctets"
  - "conversion de chaînes, caractères larges"
  - "wctomb_s (fonction)"
  - "wctomb_s_l (fonction)"
  - "caractères larges, convertir"
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# wctomb_s, _wctomb_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit le caractère large en le caractère multioctets correspondant.  Il s'agit de versions de [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 \[out\] `pRetValue`  
 Le nombre d'octets, ou un code indiquant le résultat.  
  
 \[out\] `mbchar`  
 L'adresse d'un caractère multioctets.  
  
 \[in\] `sizeInBytes`  
 Taille de la mémoire tampon `mbchar`.  
  
 \[in\] `wchar`  
 Un caractère large.  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si l'opération a réussi, code d'erreur en cas de échec.  
  
 Conditions d'erreur  
  
|`mbchar`|`sizeInBytes`|Valeur de retour|`pRetValue`|  
|--------------|-------------------|----------------------|-----------------|  
|`NULL`|\>0|`EINVAL`|non modifié|  
|any|\>`INT_MAX`|`EINVAL`|non modifié|  
|any|trop petit|`EINVAL`|non modifié|  
  
 Si l'une de ces conditions d'erreur ci\-dessus se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `wctomb` renvoie `EINVAL` et attribue à `errno` la valeur `EINVAL`.  
  
## Notes  
 La fonction `wctomb_s` convertit son argument `wchar` en le caractère multioctets correspondant et stocke le résultat dans `mbchar`.  Vous pouvez appeler la fonction de n'importe quel point dans tout programme.  
  
 Si `wctomb_s` convertit le caractère large en un caractères multioctets, il met le nombre d'octets \(qui n'est jamais supérieur à `MB_CUR_MAX`\) du caractère large dans l'entier référencé par `pRetValue`.  Si `wchar` est le caractère large caractère null \(L '\\0\), `wctomb_s` remplit `pRetValue` à 1.  Si le pointeur cible `mbchar` est NULL, `wctomb_s` met 0 dans `pRetValue`.  Si la conversion n'est pas possible dans les paramètres régionaux actuels, `wctomb_s` met – 1 dans `pRetValue`.  
  
 `wctomb_s` utilise les paramètres régionaux actuels pour les informations dépendant des paramètres régionaux ; `_wctomb_s_l` est identique à la différence qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h\>|  
|`_wctomb_s_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Ce programme illustre le comportement de la fonction `wctomb`.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
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