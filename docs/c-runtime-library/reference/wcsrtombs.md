---
title: "wcsrtombs | Microsoft Docs"
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
  - "wcsrtombs"
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
  - "wcsrtombs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcsrtombs (fonction)"
  - "conversion de chaînes, caractères larges"
  - "caractères larges, chaînes"
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une chaîne de caractères larges en sa représentation de chaîne de caractères multioctets.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [wcsrtombs\_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## Syntaxe  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `mbstr`  
 L'emplacement de l'adresse de la chaîne de caractères multioctets convertie résultante.  
  
 \[in\] `wcstr`  
 Pointe indirectement vers l'emplacement de la chaîne de caractères larges à convertir.  
  
 \[in\] `count`  
 Nombre de caractères à convertir.  
  
 \[in\] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t` .  
  
## Valeur de retour  
 Retourne le nombre d'octets correctement convertis, à l'exclusion de l'octet null de fin \(s'il existe\), sinon \-1 si une erreur se produit.  
  
## Notes  
 La fonction `wcsrtombs` convertit une chaîne de caractères larges, depuis l'état de conversion spécifié contenu dans `mbstate`, depuis les valeurs indirectement référencées dans `wcstr`, dans l'adresse de `mbstr`.  La conversion se poursuit pour chaque caractère jusqu'à ce que : après avoir rencontré un caractère large de fin null, ou si le caractère suivant excède la limite contenue dans `count`.  Si `wcsrtombs` rencontre le caractère large null \(L'\\0'\) avant ou lorsque `count` arrive, il le convertit en un zéro de 8 bits et s'arrête.  
  
 Par conséquent, la chaîne de caractères multioctets à `mbstr` se termine par null uniquement si `wcsrtombs` rencontre un caractère NULL de caractères larges lors de la conversion.  Si les séquences désignées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcsrtombs` n'est pas défini.  `wcsrtombs` est affecté par la catégorie LC\_TYPE des paramètres régionaux actuels.  
  
 La fonction `wcsrtombs` diffère de [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) par sa capacité à redémarrer.  L'état de conversion est stocké dans `mbstate` pour d'autres appels à la même ou a d'autres fonctions redémarrable.  Les résultats sont indéfinis lorqu'on mélange l'utilisation de fonctions redémarrable et non redémarrable.  Par exemple, une application utilise `wcsrlen` plutôt que `wcsnlen`, si l'appel suivant à `wcsrtombs` est utilisé à la place de `wcstombs`  
  
 Si l'argument `mbstr` est `NULL`, `wcsrtombs` retourne la taille requise en octets de la chaine de destination.  Si `mbstate` est NULL, l'état de conversion interne `mbstate_t` est utilisé.  Si la séquence de caractères `wchar` n'a pas une représentation correspondante en caractères multioctets, \-1 est retourné et `errno` est défini à la valeur `EILSEQ`.  
  
 En C\+\+, cette fonction a une surcharge de modèle qui appelle les équivalents plus récents et sécurisés de cette fonction.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Exceptions  
 La fonction `wcsrtombs` est multithread\-safe à condition qu'aucune fonction du thread actuel n'appelle `setlocale` lorsque cette fonction s'exécute et que `mbstate` n'est pas null.  
  
## Exemple  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
  **La chaîne a été correctement convertie.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h\>|  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)