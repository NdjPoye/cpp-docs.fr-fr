---
title: "wcrtomb_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb_s"
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
  - "wcrtomb_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "caractères larges, conversion"
  - "wcrtomb_s (fonction)"
  - "caractères multioctets"
  - "conversion des caractères"
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# wcrtomb_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir un caractère large en sa représentation sous forme de caractères multioctets. Une version de [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) avec des améliorations de sécurité comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `pReturnValue`  
 Retourne le nombre d’octets écrits ou \-1 si une erreur s’est produite.  
  
 \[out\] `mbchar`  
 Le multioctets résultant convertis en caractères.  
  
 \[in\] `sizeOfmbchar`  
 La taille de la `mbchar` variable en octets.  
  
 \[in\] `wchar`  
 Caractère large à convertir.  
  
 \[in\] `mbstate`  
 Pointeur vers un objet `mbstate_t`.  
  
## Valeur de retour  
 Retourne zéro ou un `errno` valeur si une erreur se produit.  
  
## Notes  
 Le `wcrtomb_s` fonction convertit un caractère large, à compter de l’état de la conversion spécifiée contenue dans `mbstate`, à partir de la valeur contenue dans `wchar`, à l’adresse représentée par `mbchar`. Le `pReturnValue` valeur sera le nombre d’octets convertis, mais pas plus de `MB_CUR_MAX` octets, ou une valeur \-1 si une erreur s’est produite.  
  
 Si `mbstate` a la valeur null, le texte interne `mbstate_t` état de la conversion est utilisé. Si le caractère figurant `wchar` ne dispose pas d’un caractère multioctet correspondant, la valeur de `pReturnValue` sera \-1 et la fonction retournera le `errno` valeur `EILSEQ`.  
  
 Le `wcrtomb_s` fonction diffère de [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables. Par exemple, une application utilise `wcsrlen` plutôt que `wcslen`, si un appel ultérieur à `wcsrtombs_s` ont été utilisés au lieu de `wcstombs_s.`  
  
 En C\+\+, l’utilisation de cette fonction est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(inutile de spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées avec leurs équivalents plus récents et sécurisés. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Exceptions  
 Le `wcrtomb_s` fonction est multithread\-safe tant qu’aucune fonction dans le thread actuel n’appelle `setlocale` pendant l’exécution de cette fonction et le `mbstate` est null.  
  
## Exemple  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
Le caractère large correspondant « Q » a été converti en un le caractère multioctet « Q ».  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h\>|  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)