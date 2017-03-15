---
title: "printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_s_l"
  - "wprintf_s"
  - "_wprintf_s_l"
  - "printf_s"
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
  - "wprintf_s"
  - "printf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_s_l (fonction)"
  - "_tprintf_s (fonction)"
  - "_tprintf_s_l (fonction)"
  - "_wprintf_s_l (fonction)"
  - "texte mis en forme (C++)"
  - "printf (fonction), champs de spécification de format"
  - "printf (fonction), utilisation"
  - "printf_s (fonction)"
  - "printf_s_l (fonction)"
  - "tprintf_s (fonction)"
  - "tprintf_s_l (fonction)"
  - "wprintf_s (fonction)"
  - "wprintf_s_l (fonction)"
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit la sortie mise en forme dans le flux de sortie standard.  Ces versions [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int printf_s(  
   const char *format [,  
   argument]...   
);  
int _printf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_s_l(  
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
 Retourne le nombre de caractères imprimés, ou une valeur négative si une erreur se produit.  
  
## Notes  
 La fonction `printf_s` met en forme une série de caractères et de valeurs et l'affiche dans le flux de sortie standard, `stdout`.  Si les arguments suivent la chaîne *format*, la chaîne `format` doit contenir des spécifications qui déterminent le format de sortie des arguments.  
  
 La principale différence entre `printf_s` et `printf` est que `printf_s` vérifie si la chaîne de format comporte des caractères de mise en forme valides, tandis que `printf` vérifie uniquement si la chaîne est un pointeur nul .  Si l'une ou l'autre vérification échoue, un gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
 Pour plus d'informations sur `errno` et ces codes d'erreur, consultez [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `printf_s` et`fprintf_s` ont un comportement identique. Toutefois `printf_s` écrit sa sortie dans `stdout` et non dans une destination de type `FILE`.  Pour plus d'informations, consultez [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).  
  
 `wprintf_s` est une version à caractères larges de `printf_s` ; `format` est une chaîne à caractères larges.  `wprintf_s` et `printf_s` se comportent de la même façon si le flux est ouvert en mode ANSI.  `printf_s` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_unicode défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tprintf_s`|`printf_s`|`printf_s`|`wprintf_s`|  
|`_tprintf_s_l`|`_printf_s_l`|`_printf_s_l`|`_wprintf_s_l`|  
  
 L'argument `format` se compose de caractères ordinaires, de séquences d'échappement et \(si des arguments suivent `format`\) de spécifications de format.  Les caractères et séquences d'échappement ordinaires sont copiés vers `stdout` dans l'ordre d'apparition.  Par exemple, la ligne  
  
```  
printf_s("Line one\n\t\tLine two\n");   
```  
  
 produit la sortie  
  
```  
Line one  
        Line two  
```  
  
 Les [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) commencent toujours par un signe de pourcentage \(`%`\) et sont lues de gauche à droite.  Lorsque `printf_s` rencontre la première spécification de format \(le cas échéant\), il convertit la valeur du premier argument après `format` et le sort en conséquence.  La deuxième spécification de format entraîne la conversion et la sortie du deuxième argument, et ainsi de suite.  S'il existe plus d'arguments que de spécifications de format, les arguments supplémentaires sont ignorés.  Les résultats sont indéfinis s'il n'y a pas assez d'arguments pour toutes les spécifications de format.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`printf_s`, `_printf_s_l`|\<stdio.h\>|  
|`wprintf_s`, `_wprintf_s_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_printf_s.c  
/* This program uses the printf_s and wprintf_s functions  
 * to produce formatted output.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   char   ch = 'h', *string = "computer";  
   int    count = -9234;  
   double fp = 251.7366;  
   wchar_t wch = L'w', *wstring = L"Unicode";  
  
   /* Display integers. */  
   printf_s( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",  
           count, count, count );  
  
   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   /* Display in different radixes. */  
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   /* Display characters. */  
  
   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);  
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);  
  
   /* Display strings. */  
  
   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",  
   string, string, wstring, wstring);  
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",  
       string, string, wstring, wstring);  
  
   /* Display real numbers. */  
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );  
  
   /* Display pointer. */  
   printf_s( "\nAddress as:   %p\n", &count);  
  
}  
```  
  
## Résultat de l'exemple  
  
```  
Integer formats:  
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062  
Decimal -9234 as:  
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756  
Digits 10 equal:  
   Hex: 16  Octal: 8  Decimal: 10  
Characters in field (1):  
         h    h    w    w  
Characters in field (2):  
         h    h    w    w  
Strings in field (1):  
                 computer  
                     comp  
   Unicode                      Uni  
Strings in field (2):  
                 computer  
                     comp  
   Unicode                      Uni  
Real numbers:  
   251.736600 251.74 2.517366e+002 2.517366E+002  
  
Address as:   0012FF78  
  
```  
  
## Équivalent .NET Framework  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Fonctions vprintf](../../c-runtime-library/vprintf-functions.md)