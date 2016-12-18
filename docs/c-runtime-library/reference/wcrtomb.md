---
title: "wcrtomb | Microsoft Docs"
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
  - "wcrtomb"
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
  - "wcrtomb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "caractères, convertir"
  - "caractères multioctets"
  - "wcrtomb (fonction)"
  - "caractères larges, convertir"
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcrtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir un caractère large dans sa représentation de caractères multioctets.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## Syntaxe  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `mbchar`  
 Le caractère converti multioctets résultant.  
  
 \[in\] `wchar`  
 Caractère large à convertir.  
  
 \[in\] `mbstate`  
 Pointeur vers un objet `mbstate_t`.  
  
## Valeur de retour  
 Retourne le nombre d'octets requis pour représenter les caractères multioctets convertis, sinon a \-1 si une erreur se produit.  
  
## Notes  
 La fonction `wcrtomb` convertit un caractère large, commençant dans l'état de conversion spécifié contenu dans `mbstate`, depuis la valeur contenue dans `wchar`, dans l'adresse représentée par `mbchar`.  La valeur renvoyée est le nombre d'octets requis pour représenter les caractères multioctets correspondant, mais il ne retourne plus que `MB_CUR_MAX` octets.  
  
 Si `mbstate` est NULL, l'objet interne `mbstate_t` contenant l'état de conversion de `mbchar` est utilisé.  Si la séquence de caractères `wchar` n'a pas une représentation correspondante en caractères multioctets, \-1 est retourné et `errno` est défini à la valeur `EILSEQ`.  
  
 La fonction `wcrtomb` diffère de [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) par sa capacité à redémarrer.  L'état de conversion est stocké dans `mbstate` pour d'autres appels à la même ou a d'autres fonctions redémarrable.  Les résultats sont indéfinis lorsqu'on mélange l'utilisation de fonctions redémarrable et non redémarrable.  Par exemple, une application utilise `wcsrlen` plutôt que`wcsnlen`, si l'appel suivant à `wcsrtombs` est utilisé à la place de`wcstombs`  
  
 En C\+\+, cette fonction a une surcharge de modèle qui appelle les équivalents plus récents et sécurisés de cette fonction.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Exceptions  
 La fonction `wcrtomb` est multithread\-safe à condition qu'aucune fonction du thread actuel n'appelle `setlocale` lorsque cette fonction s'exécute et lorsque `mbstate` est null.  
  
## Exemple  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
  **Le caractère large correspondant « Q » a été converti en caractères multioctets « Q ».**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h\>|  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)