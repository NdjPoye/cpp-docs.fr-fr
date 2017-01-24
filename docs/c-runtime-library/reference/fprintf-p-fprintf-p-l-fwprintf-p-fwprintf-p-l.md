---
title: "_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l | Microsoft Docs"
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
  - "_fwprintf_p"
  - "_fprintf_p_l"
  - "_fwprintf_p_l"
  - "_fprintf_p"
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
  - "_fprintf_p"
  - "_ftprintf_p"
  - "fwprintf_p"
  - "_fwprintf_p"
  - "fprintf_p"
  - "ftprintf_p"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fprintf_p (fonction)"
  - "_fprintf_p_l (fonction)"
  - "_ftprintf_p (fonction)"
  - "_ftprintf_p_l (fonction)"
  - "_fwprintf_p (fonction)"
  - "_fwprintf_p_l (fonction)"
  - "fprintf_p (fonction)"
  - "fprintf_p_l (fonction)"
  - "ftprintf_p (fonction)"
  - "ftprintf_p_l (fonction)"
  - "fwprintf_p (fonction)"
  - "fwprintf_p_l (fonction)"
  - "imprimer (C++), données mises en forme dans les flux"
  - "flux, imprimer des données mises en forme dans"
ms.assetid: 46b082e1-45ba-4383-9ee4-97015aa50bc6
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne des données mises en forme dans les flux  
  
## Syntaxe  
  
```  
int _fprintf_p(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_p_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int _fwprintf_p(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_p_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...  
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_fprintf_p` et `_fwprintf_p` retourneent le nombre de caractères entrés ou retournent une valeur négative lorsqu'une erreur de sortie se produit.  
  
## Notes  
 La fonction `_fprintf_p` met en forme et retourne une série de caractères et de valeurs en sortie `stream` Chaque fonction `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`.  Pour `_fprintf_p`, l'argument `format` a la même syntaxe et utilisation que dans `_printf_p`.  Elles prennent en charge les paramètres positionnels, ce qui signifie que l'ordre des paramètres utilisés par la chaîne de format peut être modifiée.  Pour plus d'informations sur les paramètres positionnels, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_fwprintf_p` est une version à caractères larges de `_fprintf_p` ; dans `_fwprintf_p`, `format` est une chaîne à caractères larges.  Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `_fprintf_p` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 Comme les versions non sécurisés \(consultez [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)\), ces fonctions valident leurs paramètres et appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md), si `stream` ou `format` est un pointeur null ou si elle est inconnue ou des specificateurs de format mal formés.  Si l'exécution est autorisée à se poursuivre, cette fonction renvoient \-1 et définie `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_ftprintf_p`|`_fprintf_p`|`_fprintf_p`|`_fwprintf_p`|  
|`_ftprintf_p_l`|`_fprintf_p_l`|`_fprintf_p_l`|`_fwprintf_p_l`|  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fprintf_p`, `_fprintf_p_l`|\<stdio.h\>|  
|`_fwprintf_p`, `_fwprintf_p_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fprintf_p.c  
// This program uses _fprintf_p to format various  
// data and print it to the file named FPRINTF_P.OUT. It  
// then displays FPRINTF_P.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
//   
  
#include <stdio.h>  
#include <process.h>  
  
int main( void )  
{  
    FILE    *stream = NULL;  
    int     i = 10;  
    double  fp = 1.5;  
    char    s[] = "this is a string";  
    char    c = '\n';  
  
    // Open the file  
    if ( fopen_s( &stream, "fprintf_p.out", "w" ) == 0)  
    {  
        // Format and print data  
        _fprintf_p( stream, "%2$s%1$c", c, s );  
        _fprintf_p( stream, "%d\n", i );  
        _fprintf_p( stream, "%f\n", fp );  
  
        // Close the file  
        fclose( stream );  
    }  
  
    // Verify our data  
    system( "type fprintf_p.out" );  
}  
```  
  
  **Il s'agit d'une chaîne.**  
**10**  
**1.500000**   
## Équivalent .NET Framework  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)