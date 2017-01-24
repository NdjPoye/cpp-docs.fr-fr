---
title: "_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs"
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
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_swprintf_p"
  - "_sprintf_p_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_sprintf_p_l"
  - "_swprintf_p"
  - "sprintf_p"
  - "swprint_p_l"
  - "swprintf_p"
  - "swprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "sprintf_p_l (fonction)"
  - "swprintf_p (fonction)"
  - "swprintf_p_l (fonction)"
  - "_sprintf_p (fonction)"
  - "_sprintf_p_l (fonction)"
  - "_swprintf_p (fonction)"
  - "sprintf_p (fonction)"
  - "_stprintf_p (fonction)"
  - "stprintf_p (fonction)"
  - "_swprintf_p_l (fonction)"
  - "stprintf_p_l (fonction)"
  - "texte mis en forme (C++)"
  - "_stprintf_p_l (fonction)"
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entrez les données mises en forme dans une chaîne avec la possibilité de spécifier l'ordre dans lequel les paramètres sont utilisés dans la chaîne de format.  
  
## Syntaxe  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] …   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour la sortie  
  
 `sizeOfBuffer`  
 Nombre maximal de caractères à stocker.  
  
 `format`  
 Chaîne de contrôle de format  
  
 `argument`  
 Arguments facultatifs  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Nombre de caractères écrits, ou –1 si une erreur s'est produite.  
  
## Notes  
 La fonction `_sprintf_p`  met en forme une série de caractères et de valeurs et la stocke dans `buffer`.  Chaque `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`.  Le format se compose de caractères ordinaires et a la même forme et fonction que l'argument `format` pour `printf_p`.  Un caractère `NULL` est ajouté après le dernier caractère écrit.  Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  La différence entre `_sprintf_p` et `sprintf_s` est que `_sprintf_p` prend en charge les paramètres positionnels, qui permettent de spécifier l'ordre dans lequel les arguments sont utilisés dans la chaîne de format.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_swprintf_p` est une version à caractères larges de `_sprintf_p` ; les arguments de pointeur de `_swprintf_p` sont des chaînes à caractères larges.  La détection d'erreurs d'encodage dans `_swprintf_p` peut différer de celle dans `_sprintf_p`.  `_swprintf_p` et `fwprintf_p` ont un comportement identique, sauf que `_swprintf_p` écrit la sortie dans une chaîne au lieu d'une destination de type `FILE`, et que `_swprintf_p` nécessite que le paramètre `count`spécifie le nombre maximal de caractères à écrire.  Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 `_sprintf_p` retourne le nombre d'octets stockés dans `buffer`, sans compter le caractère `NULL` de fin.  `_swprintf_p`retourne le nombre de caractères larges stockés dans `buffer`, sans compter le caractère large `NULL` de fin.  Si `buffer` ou `format` est un pointeur null, ou si la chaîne de format contient des caractères de mise en forme valides, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et attribuent à `errno` la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h\>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
  **Sortie :**  
 **String:    computer**  
 **Character: l**  
 **Integer:   35**  
 **Real:      1.732053**  
**character count \= 79**   
## Exemple  
  
```  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
  **a écrit 24 characters**  
**a écrit \-1 characters**   
## Équivalent .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)