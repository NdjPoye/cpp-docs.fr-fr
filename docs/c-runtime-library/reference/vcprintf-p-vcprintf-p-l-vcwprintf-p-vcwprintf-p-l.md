---
title: "_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcprintf_p"
  - "_vcwprintf_p_l"
  - "_vcprintf_p_l"
  - "_vcwprintf_p"
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
  - "vcwprintf_p"
  - "vcprintf_p_l"
  - "_vcprintf_p"
  - "_vcprintf_p_l"
  - "vcwprintf_p_l"
  - "vcprintf_p"
  - "_vcwprintf_p"
  - "_vcwprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vcprintf_p (fonction)"
  - "_vcprintf_p_l (fonction)"
  - "_vcwprintf_p (fonction)"
  - "_vcwprintf_p_l (fonction)"
  - "_vtcprintf_p (fonction)"
  - "_vtcprintf_p_l (fonction)"
  - "vcprintf_p (fonction)"
  - "vcprintf_p_l (fonction)"
  - "vcwprintf_p (fonction)"
  - "vcwprintf_p_l (fonction)"
  - "vtcprintf_p (fonction)"
  - "vtcprintf_p_l (fonction)"
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit la sortie mise en forme dans la console en utilisant un pointeur désignant une liste d'arguments et prend en charge les paramètres de position dans la chaîne de format.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _vcprintf_p(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_p_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_p(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_p_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### Paramètres  
 `format`  
 Spécification du format.  
  
 `argptr`  
 Pointeur désignant une liste d'arguments.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
 Pour plus d'informations, consultez [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Valeur de retour  
 Nombre de caractères écrits ou valeur négative en cas d'erreur de sortie.  Si `format` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et \-1 est retourné.  
  
## Notes  
 Chacune de ces fonctions prend un pointeur désignant une liste d'arguments, puis utilise la fonction `_putch` pour mettre en forme et écrire les données en question dans la console.  \(`_vcwprintf_p` utilise `_putwch` à la place de `_putch`.  `_vcwprintf_p` est la version à caractères larges de `_vcprintf_p`.  Elle prend une chaîne de caractères larges comme argument.\)  
  
 Les versions de ces fonctions qui ont le suffixe `_l` sont identiques, à ceci près qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actifs.  
  
 Chaque `argument` \(le cas échéant\) est converti et sorti selon la spécification de format correspondante dans `format`.  La spécification de format prend en charge les paramètres positionnels, ce qui vous permet de spécifier l'ordre dans lequel les arguments sont utilisés dans la chaîne de format.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Ces fonctions ne traduisent par les caractères de saut de ligne en combinaisons retour chariot\-saut de ligne au moment de leur sortie.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  Pour plus d'informations, voir [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Ces fonctions valident le pointeur d'entrée et la chaîne de format.  Si `format` ou `argument` a la valeur `NULL` ou si la chaîne de format contient des caractères de mise en forme non valides, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_vtcprintf_p`|`_vcprintf_p`|`_vcprintf_p`|`_vcwprintf_p`|  
|`_vtcprintf_p_l`|`_vcprintf_p_l`|`_vcprintf_p_l`|`_vcwprintf_p_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_vcprintf_p`, `_vcprintf_p_l`|\<conio.h\> et \<stdarg.h\>|  
|`_vcwprintf_p`, `_vcwprintf_p_l`|\<conio.h\> et \<stdarg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_vcprintf_p.c  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function that's used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf_p(format, args);  
}  
  
int main()  
{  
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",  
      "one", 222);  
   _cprintf_s("%d characters printed\r\n");  
}  
```  
  
  **parameter 2 \= 222; parameter 1 \= one**  
**38 characters printed**   
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)