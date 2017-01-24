---
title: "_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l | Microsoft Docs"
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
  - "_cprintf_p_l"
  - "_cwprintf_p_l"
  - "_cwprintf_p"
  - "_cprintf_p"
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
  - "cprintf_p"
  - "cwprintf_p"
  - "tcprintf_p"
  - "_cwprintf_p_l"
  - "_cprintf_p"
  - "csprintf_p_l"
  - "_cprintf_p_l"
  - "_cwprintf_p"
  - "_tcprintf_p"
  - "cprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cprintf_p (fonction)"
  - "_cprintf_p_l (fonction)"
  - "_cwprintf_p (fonction)"
  - "_cwprintf_p_l (fonction)"
  - "_tcprintf_p (fonction)"
  - "_tcprintf_p_l (fonction)"
  - "cprintf_p (fonction)"
  - "cprintf_p_l (fonction)"
  - "cwprintf_p (fonction)"
  - "cwprintf_p_l (fonction)"
  - "tcprintf_p (fonction)"
  - "tcprintf_p_l (fonction)"
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Met en forme et affiche les informations sur la console, et prend en charge les paramètres positionnels dans la chaîne de format.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _cprintf_p(   
   const char * format [,   
   argument] ...   
);  
int _cprintf_p_l(   
   const char * format,  
   locale_t locale [,   
   argument] ...   
);  
int _cwprintf_p(  
   const wchar * format [,   
   argument] ...  
);  
int _cwprintf_p_l(  
   const wchar * format,  
   locale_t locale [,  
   argument] ...  
);  
```  
  
#### Paramètres  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Paramètres facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Nombre de caractères affichés ou valeur négative en cas d'erreur.  
  
## Notes  
 Ces fonctions mettent en forme et affichent toute une série de caractères et de valeurs directement dans la console, en se servant des fonctions `_putch` et `_putwch` pour effectuer la sortie des caractères.  Chaque `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`.  Le format a la même forme et la même fonction que le paramètre `format` pour la fonction [printf\_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  La différence entre `_cprintf_p` et `cprintf_s` vient du fait que `_cprintf_p` prend en charge les paramètres positionnels, ce qui vous permet de spécifier l'ordre dans lequel les arguments sont utilisés dans la chaîne de format.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Contrairement aux fonctions `fprintf_p`, `printf_p` et `sprintf_p`, les fonctions `_cprintf_p` et `_cwprintf_p` ne traduisent pas les caractères de saut de ligne en combinaisons retour chariot\-saut de ligne à leur sortie.  Il existe une différence importante : `_cwprintf_p` affiche les caractères Unicode dans Windows NT.  Contrairement à `_cprintf_p`, `_cwprintf_p` utilise les paramètres régionaux de la console active.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 En outre, tout comme `_cprintf_s` et `_cwprintf_s`, elles valident le pointeur d'entrée et la chaîne de format.  Si `format` ou `argument` a la valeur `NULL`, ou si la chaîne de format contient des caractères de mise en forme non valides, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcprintf_p`|`_cprintf_p`|`_cprintf_p`|`_cwprintf_p`|  
|`_tcprintf_p_l`|`_cprintf_p_l`|`_cprintf_p_l`|`_cwprintf_p_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cprintf_p`,`_cprintf_p_l`|\<conio.h\>|  
|`_cwprintf_p`,`_cwprintf_p_l`|\<conio.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_cprintf_p.c  
// This program displays some variables to the console  
// using the _cprintf_p function.  
  
#include <conio.h>  
  
int main( void )  
{  
    int         i = -16,  
                h = 29;  
    unsigned    u = 62511;  
    char        c = 'A';  
    char        s[] = "Test";  
  
    // Note that console output does not translate  
    // \n as standard output does. Use \r\n instead.  
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",   
                h, i, u, c, s );  
}  
```  
  
  **\-16  001d  62511  A Test**   
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)