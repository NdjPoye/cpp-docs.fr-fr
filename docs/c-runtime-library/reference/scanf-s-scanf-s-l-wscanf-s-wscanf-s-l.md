---
title: "scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wscanf_s"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_scanf_s_l"
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
  - "wscanf_s"
  - "_tscanf_s_l"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_tscanf_s"
  - "_scanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lecture de données (C++), à partir de flux d’entrée"
  - "mémoires tampons [C++], dépassements de mémoire tampon"
  - "_scanf_s_l (fonction)"
  - "_wscanf_s_l (fonction)"
  - "tscanf_s_l (fonction)"
  - "tscanf_s (fonction)"
  - "scanf_s (fonction)"
  - "lecture du flux d’entrée de données (C++),"
  - "wscanf_s (fonction)"
  - "_tscanf_s_l (fonction)"
  - "_tscanf_s (fonction)"
  - "scanf_s_l (fonction)"
  - "données mises en forme (C++), à partir de flux d’entrée"
  - "wscanf_s_l (fonction)"
  - "mémoires tampons [C++], éviter les dépassements"
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données mises en forme du flux d'entrée standard. Ces versions de [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) ont des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Paramètres  
 `format`  
 Format de la chaîne de contrôle.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne le nombre de champs correctement convertis et assignés. La valeur de retour n'inclut pas les champs qui ont été lus mais pas assignés. La valeur de retour 0 indique qu'aucun champ n'a été assigné. La valeur de retour est `EOF` si une erreur est détectée, ou si le caractère de fin de fichier ou le caractère de fin de chaîne est rencontré durant la première tentative de lecture d'un caractère. Si `format` est un `NULL` du pointeur, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, `scanf_s` et `wscanf_s` retournent `EOF` et définissent `errno` à `EINVAL`.  
  
 Pour plus d’informations sur ces codes et d’autres codes d’erreur, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `scanf_s` lit les données du flux d'entrée standard `stdin` et les écrit dans l'emplacement indiqué par `argument`. Chaque `argument` doit être un pointeur vers une variable d'un type qui correspond à un spécificateur de type dans `format`. Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 `wscanf_s` est une version à caractères larges de `scanf_s` ; l'argument `format` de `wscanf_s` est une chaîne à caractères larges.`wscanf_s` et `scanf_s` se comportent de la même façon si le flux est ouvert en mode ANSI.`scanf_s` ne prend pas en charge actuellement les entrées à partir d'un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
 Contrairement à `scanf` et `wscanf`, `scanf_s` et `wscanf_s` nécessitent que la taille de la mémoire tampon soit spécifiée pour tous les paramètres d'entrée de type `c`, `C`, `s`, `S`, ou pour les jeux de contrôles de chaîne entre `[]`. La taille de la mémoire tampon en caractères est passée en tant que paramètre supplémentaire immédiatement après le pointeur vers la mémoire tampon ou la variable. Par exemple, si vous lisez une chaîne, la taille de la mémoire tampon pour cette chaîne est passée comme suit :  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 La taille de la mémoire tampon inclut le caractère Null de fin. Vous pouvez utiliser un champ de spécification de largeur pour vous assurer que le jeton lu sera contenu sans problème en mémoire tampon. Si aucun champ de spécification de largeur n'est utilisé, et si le jeton lu est trop grand pour la mémoire tampon, aucune valeur n'est écrite dans cette mémoire tampon.  
  
> [!NOTE]
>  Le paramètre relatif à la taille est de type `unsigned`, et non `size_t`. Utilisez un cast statique pour convertir un `size_t` valeur `unsigned` 64 bits des configurations de build.  
  
 L'exemple suivant montre que le paramètre relatif à la taille de la mémoire tampon décrit le nombre maximal de caractères, et non d'octets. Dans l'appel à `wscanf_s`, la largeur des caractères indiquée par le type de mémoire tampon ne correspond pas à la largeur des caractères indiquée par le spécificateur de format.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 Le spécificateur de format `S` indique l'utilisation de la largeur des caractères « inverse » à la largeur par défaut prise en charge par la fonction. La largeur des caractères est basée sur les caractères codés sur un octet, mais la fonction prend en charge les caractères codés sur deux octets. Cet exemple lit une chaîne d'une largeur maximale de 9 caractères codés sur un octet, et les place dans une mémoire tampon dont la largeur est basée sur des caractères codés sur deux octets. Les caractères sont traités comme des valeurs codées sur un octet. Les deux premiers caractères sont stockés dans `ws[0]`, alors que les deux derniers sont stockés dans `ws[1]`, et ainsi de suite.  
  
 Dans le cas des caractères, un caractère unique peut être lu comme suit :  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 Durant la lecture de plusieurs caractères pour les chaînes qui ne se terminent pas par une valeur Null, des entiers sont utilisés pour la spécification de la largeur et la taille de la mémoire tampon.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Pour plus d'informations, consultez [Spécification de largeur scanf](../../c-runtime-library/scanf-width-specification.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 Pour plus d'informations, consultez [Champs de spécification de format : fonctions scanf et wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h\>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console \(`stdin`, `stdout` et `stderr`\) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 Ce programme génère la sortie suivante en fonction de ce qui est entré :  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
Le nombre de champs entrée est 6, le contenu est : 71 z h 98.599998 octets de caractères le nombre de champs d’entrée est le contenu est de 6 : 36 92.300003 y de n caractères larges  
```  
  
## Équivalent .NET Framework  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   Voir aussi `Parse` méthodes, telles que [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)