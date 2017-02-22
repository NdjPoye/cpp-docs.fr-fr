---
title: "wcstombs, _wcstombs_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstombs"
  - "_wcstombs_l"
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
  - "wcstombs"
  - "_wcstombs_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wcstombs_l (fonction)"
  - "caractères, convertir"
  - "conversion de chaînes, chaînes de caractères multioctets"
  - "conversion de chaînes, caractères larges"
  - "wcstombs (fonction)"
  - "wcstombs_l (fonction)"
  - "caractères larges, convertir"
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# wcstombs, _wcstombs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit la séquence de caractères multioctets en la séquence correspondante de caractères larges.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## Syntaxe  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `mbstr`  
 L'adresse d'une séquence de caractères multioctets.  
  
 `wcstr`  
 L'adresse d'une séquence de caractères larges.  
  
 `count`  
 Le nombre maximal d'octets qui peuvent être stockés dans la chaîne de sortie multioctets.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Si `wcstombs` convertit correctement la chaîne multioctets, elle retourne le nombre d'octets écrits dans la chaîne de sortie multioctets, à l'exception du `NULL` de fin \(le cas échéant\).  Si l'argument `mbstr` est `NULL`, `wcstombs` retourne la taille requise en octets de la chaine de destination.  Si `wcstombs` rencontre un caractère large qu'il ne peut pas convertir en caractères multioctets, il retourne – 1 converti en type `size_t` et définit `errno` à `EILSEQ`.  
  
## Notes  
 La fonction `wcstombs` convertit la chaîne de caractères larges désignée par `wcstr` en les caractères multioctets correspondants et stocke les résultats dans le tableau `mbstr`.  Le paramètre `count` indique le nombre maximal d'octets qui peuvent être stockés dans la chaîne de sortie multioctets \(autrement dit, la taille de `mbstr`\).  En général, on ne sait pas combien d'octets sont requis quand on convertit une chaîne de caractères larges.  Certains caractères larges ont besoin d'un seul octet dans la chaîne de sortie ; d'autres nécessitent deux.  S'il existe deux octets dans la chaîne de sortie multioctets pour chaque caractère large dans la chaîne d'entrée caractère large \(y compris le caractère large `NULL`\), le résultat est garanti de s'ajuster.  
  
 Si `wcstombs` rencontre le caractère NULL de caractères étendus \(L '\\0\) avant ou lorsque `count` arrive, il le convertit en un 0 de 8 bits et s'arrête.  Par conséquent, la chaîne de caractères multioctets à `mbstr` se termine par null uniquement si `wcstombs` rencontre un caractère NULL de caractères larges lors de la conversion.  Si les séquences désignées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcstombs` n'est pas défini.  
  
 Si l'argument `mbstr` est `NULL`, `wcstombs` retourne la taille requise en octets de la chaine de destination.  
  
 `wcstombs` valide ses paramètres.  Si `wcstr` est `NULL`, ou si `count` est supérieur à`INT_MAX`, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction définit `errno` à la valeur `EINVAL` et retourne \-1.  
  
 `wcstombs` utilise les paramètres régionaux actuels pour tout comportement dépend des paramètres régionaux ; `_wcstombs_l` est identique à la différence qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h\>|  
|`_wcstombs_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Ce programme illustre le comportement de la fonction `wcstombs`.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
  **Convertit la chaîne à caractères élargis:**  
 **Caractères convertis : 13**  
 **Caractères multioctets : Hello world.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)