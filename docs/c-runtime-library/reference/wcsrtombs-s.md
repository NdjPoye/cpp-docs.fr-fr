---
title: "wcsrtombs_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsrtombs_s"
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
  - "wcsrtombs_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversion de chaînes, caractères larges"
  - "wcsrtombs_s (fonction)"
  - "caractères larges, chaînes"
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# wcsrtombs_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une chaîne de caractères larges en sa représentation de chaîne de caractères multioctets.  Il s'agit de versions de [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `pReturnValue`  
 Nombre de caractères convertis.  
  
 \[out\] `mbstr`  
 L'adresse d'un tampon pour la chaîne de caractères multioctets convertie résultante.  
  
 \[out\] `sizeInBytes`  
 La taille en octets de la mémoire tampon `mbstr`.  
  
 \[in\] `wcstr`  
 Pointe vers la chaîne de caractères larges à convertir.  
  
 \[in\] `count`  
 Nombre maximal d'octets à stocker dans la mémoire tampon `mbstr`, ou [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t` .  
  
## Valeur de retour  
 Zéro si l'opération a réussi, code d'erreur en cas de échec.  
  
|Condition d'erreur|Valeur de retour et `errno`|  
|------------------------|---------------------------------|  
|`mbstr` est `NULL` et `sizeInBytes` \> 0|`EINVAL`|  
|`wcstr` est `NULL`|`EINVAL`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie \(à moins que `count` est `_TRUNCATE`; consultez les notes ci\-dessous\)|`ERANGE`|  
  
 Si l'une de ces conditions d'erreur se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno` comme indiqué dans la table.  
  
## Notes  
 La fonction `wcsrtombs_s` convertit une chaîne de caractères larges référencés par `wcstr` en caractères multioctets stockés dans la mémoire tampon désignée par `mbstr`, en utilisant l'état de conversion contenu dans `mbstate`.  La conversion se poursuit pour chaque caractère tant qu'une des conditions suivantes est remplie :  
  
-   Un caractère large NULL est rencontré  
  
-   Un caractère large qui ne peut pas être converti est produit  
  
-   Le nombre d'octets stockés en mémoire tampon `mbstr` est égal à `count`.  
  
 La chaîne de destination est toujours terminée par null \(même en cas d'erreur\).  
  
 Si `count` est la valeur spéciale [\_TRUNCATE](../../c-runtime-library/truncate.md), alors `wcsrtombs_s` convertit autant de la chaîne que ce qui s'insérera dans la mémoire tampon de destination, tout en laissant toujours de l'espace pour une marque de fin null.  
  
 Si `wcsrtombs_s` convertit correctement la chaîne source, elle définit la taille en octets de la chaîne convertie, notamment la marque de fin null, dans `*``pReturnValue` \( dans la cas où `pReturnValue` n'est pas `NULL`\).  Cela se produit même si l'argument `mbstr` est `NULL` et permet de déterminer la taille de mémoire tampon requise.  Notez que si `mbstr` est `NULL`, `count` est ignoré.  
  
 Si `wcsrtombs_s` rencontre un caractère large qu'il ne peut pas convertir en caractères multioctets, il met \-1 dans `*``pReturnValue`, définit la mémoire tampon de destination comme une chaîne vide, définit `errno` à `EILSEQ`, et retourne `EILSEQ`.  
  
 Si les séquences désignées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcsrtombs_s` n'est pas défini.  `wcsrtombs_s` est affecté par la catégorie LC\_TYPE des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète fidèlement le nombre de caractères larges à convertir.  
  
 La fonction `wcsrtombs_s` diffère de [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) par sa capacité à redémarrer.  L'état de conversion est stocké dans `mbstate` pour d'autres appels à la même ou a d'autres fonctions redémarrable.  Les résultats sont indéfinis lorqu'on mélange l'utilisation de fonctions redémarrable et non redémarrable.  Par exemple, une application utilise `wcsrlen` plutôt que `wcslen`, si l'appel suivant à `wcsrtombs_s` est utilisé à la place de `wcstombs_s.`  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Exceptions  
 La fonction `wcsrtombs_s` est multithread\-safe à condition qu'aucune fonction du thread actuel n'appelle `setlocale` lorsque cette fonction s'exécute et que `mbstate` est null.  
  
## Exemple  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
  **La chaîne a été correctement convertie.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h\>|  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)