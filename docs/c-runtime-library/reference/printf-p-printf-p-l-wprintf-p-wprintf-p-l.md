---
title: "_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_p"
  - "_wprintf_p"
  - "_printf_p_l"
  - "_wprintf_p_l"
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
  - "wprintf_p"
  - "_wprintf_p"
  - "printf_p_l"
  - "_printf_p"
  - "printf_p"
  - "_wprintf_p_l"
  - "_printf_p_l"
  - "wprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p (fonction)"
  - "_printf_p_l (fonction)"
  - "_tprintf_p_l (fonction)"
  - "_wprintf_p (fonction)"
  - "_wprintf_p_l (fonction)"
  - "printf_p (fonction)"
  - "printf_p_l (fonction)"
  - "tprintf_p_l (fonction)"
  - "wprintf_p (fonction)"
  - "wprintf_p_l (fonction)"
ms.assetid: 1b7e9ef9-a069-45db-af9d-c2730168322e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Imprime la sortie mise en forme dans le flux de sortie standard, ainsi que la spécification de l'ordre dans lequel les paramètres sont utilisés dans la chaîne de format.  
  
## Syntaxe  
  
```  
int _printf_p(  
   const char *format [,  
   argument]...   
);  
int _printf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int _wprintf_p(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_p_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Paramètres  
 `format`  
 Contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne le nombre de caractères imprimés ou une valeur négative si une erreur se produit.  
  
## Notes  
 La fonction `_printf_p`  met en forme une série de caractères et de valeurs et l'affiche dans le flux de sortie standard, `stdout`.  Si les arguments suivent la chaîne `format`, la chaîne `format` doit contenir des spécifications qui déterminent le format de sortie des arguments \(voir [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)\)..  
  
 La différence entre `_printf_p` et `printf_s` est que `_printf_p` prend en charge les paramètres positionnels, qui permettent de spécifier l'ordre dans lequel les arguments sont utilisés dans la chaîne de format.  Pour plus d'informations, consultez [Paramètres positionnels printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_wprintf_p` est la version à caractères élargis de `_printf_p`; ils se comportent de la même manière si le flux est ouvert en mode ANSI.  `_printf_p` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 Si `format` ou `argument` sont `NULL`, ou si la chaîne de format contient des caractères de mise en forme invalides, les fonctions `_printf_p` et `_wprintf_p` appellent un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tprintf_p`|`_printf_p`|`_printf_p`|`_wprintf_p`|  
|`_tprintf_p_l`|`_printf_p_l`|`_printf_p_l`|`_wprintf_p_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_printf_p`, `_printf_p_l`|\<stdio.h\>|  
|`_wprintf_p`, `_wprintf_p_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_printf_p.c  
// This program uses the _printf_p and _wprintf_p  
// functions to choose the order in which parameters  
// are used.  
  
#include <stdio.h>  
  
int main( void )  
{  
   // Positional arguments   
   _printf_p( "Specifying the order: %2$s %3$s %1$s %4$s %5$s.\n",  
              "little", "I'm", "a", "tea", "pot");  
  
   // Resume arguments  
   _wprintf_p( L"Reusing arguments: %1$d %1$d %1$d %1$d\n", 10);  
  
   // Width argument  
   _printf_p("Width specifiers: %1$*2$s", "Hello\n", 10);  
}  
```  
  
  **Spécification d'un ordre : Je suis un petit pot de thé.**  
**Réutilisation d'arguments : 10 10 10 10**  
**Spécificateurs de largeur :     Hello**   
## Équivalent .NET Framework  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)