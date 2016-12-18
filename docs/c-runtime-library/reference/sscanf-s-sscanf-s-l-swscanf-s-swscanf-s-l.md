---
title: "sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l | Microsoft Docs"
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
  - "_sscanf_s_l"
  - "sscanf_s"
  - "_swscanf_s_l"
  - "swscanf_s"
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
  - "_stscanf_s"
  - "sscanf_s"
  - "swscanf_s"
  - "_swscanf_s_l"
  - "_stscanf_s_l"
  - "_sscanf_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sscanf_s_l (fonction)"
  - "_stscanf_s (fonction)"
  - "_stscanf_s_l (fonction)"
  - "_swscanf_s_l (fonction)"
  - "lire des données, chaînes"
  - "sscanf_s (fonction)"
  - "sscanf_s_l (fonction)"
  - "chaînes (C++), lire"
  - "chaînes (C++), lire des données à partir de"
  - "stscanf_s (fonction)"
  - "stscanf_s_l (fonction)"
  - "swscanf_s (fonction)"
  - "swscanf_s_l (fonction)"
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit des données à partir d’une chaîne au format. Ces versions de [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md) ont des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int sscanf_s(  
   const char *buffer,  
   const char *format [,  
   argument ] ...  
);  
int _sscanf_s_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...  
);  
int swscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...  
);  
int _swscanf_s_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...  
);  
```  
  
#### Paramètres  
 `buffer`  
 Données stockées  
  
 `format`  
 Chaîne de contrôle de format. Pour plus d'informations, consultez [Champs de spécification de format : fonctions scanf et wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `argument`  
 Arguments facultatifs  
  
 `locale`  
 Les paramètres régionaux à utiliser  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de champs qui sont convertis et attribués ; la valeur de retour n’inclut pas les champs qui ont été lues mais pas attribués. La valeur de retour 0 indique qu'aucun champ n'a été assigné. La valeur de retour est `EOF` pour une erreur ou si la fin de la chaîne est atteinte avant la première conversion.  
  
 Si `buffer` ou `format` est un `NULL` du pointeur, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et attribuent à `errno` la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes et d’autres codes d’erreur, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Le `sscanf_s` fonction lit les données à partir de `buffer` dans l’emplacement qui est fourni par chaque `argument`. Les arguments après la chaîne de format spécifient des pointeurs vers des variables qui ont un type qui correspond au spécificateur de type dans `format`. Contrairement à la version la moins sécurisée `sscanf`, un paramètre de taille de mémoire tampon est requis lorsque vous utilisez les caractères de champ de type `c`, `C`, `s`, `S`, ou qui sont inclus dans les jeux de contrôles de la chaîne `[]`. La taille de mémoire tampon de caractères doit être fournie comme paramètre supplémentaire immédiatement après chaque paramètre de mémoire tampon qui en a besoin. Par exemple, si vous lisez dans une chaîne, la taille du tampon pour cette chaîne est passée comme suit :  
  
 `wchar_t ws[10];`  
  
 `swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9`  
  
 La taille de la mémoire tampon inclut le caractère Null de fin. Un champ de spécification de largeur peut être utilisé pour s’assurer que le jeton qui est lu se tiendront dans la mémoire tampon. Si aucun champ de spécification de largeur n'est utilisé, et si le jeton lu est trop grand pour la mémoire tampon, aucune valeur n'est écrite dans cette mémoire tampon.  
  
 Dans le cas des caractères, un caractère unique peut être lu comme suit :  
  
 `wchar_t wc;`  
  
 `swscanf_s(in_str, L"%c", &wc, 1);`  
  
 Cet exemple lit un caractère unique dans la chaîne d’entrée et puis elle le stocke dans une mémoire tampon de caractères larges. Lorsque vous lisez plusieurs caractères pour les chaînes terminées par non null, entiers non signés sont utilisés en tant que la spécification de la largeur et la taille du tampon.  
  
 `char c[4];`  
  
 `sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Pour plus d’informations, consultez [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) et [Caractères du champ de type scanf](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Le paramètre relatif à la taille est de type `unsigned`, et non `size_t`. Lors de la compilation pour des cibles 64 bits, utilisez un cast statique pour convertir `_countof` ou `sizeof` à la taille correcte des résultats.  
  
 Le `format` contrôles d’argument des champs de l’interprétation de l’entrée et a la même forme et fonction que le `format` argument pour le `scanf_s` \(fonction\). Si une copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 `swscanf_s` est une version à caractère élargi de `sscanf_s;` les arguments de `swscanf_s` sont des chaînes à caractères larges.`sscanf_s` ne gère pas les caractères hexadécimaux multioctets.`swscanf_s` ne gère pas hexadécimal de pleine chasse Unicode ou des caractères de la « zone de compatibilité ». Sinon, `swscanf_s` et `sscanf_s` se comportent de la même façon.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_stscanf_s`|`sscanf_s`|`sscanf_s`|`swscanf_s`|  
|`_stscanf_s_l`|`_sscanf_s_l`|`_sscanf_s_l`|`_swscanf_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`sscanf_s`, `_sscanf_s_l`|\<stdio.h\>|  
|`swscanf_s`, `_swscanf_s_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_sscanf_s.c  
// This program uses sscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string plus NULL terminator  
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );  
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );  
   sscanf_s( tokenstring, "%d", &i );  
   sscanf_s( tokenstring, "%f", &fp );  
  
   // Output the data read  
   printf_s( "String    = %s\n", s );  
   printf_s( "Character = %c\n", c );  
   printf_s( "Integer:  = %d\n", i );  
   printf_s( "Real:     = %f\n", fp );  
}  
```  
  
```Output  
Chaîne = 15 caractères = 1 entier : = 15 réel : = 15.000000  
```  
  
## Équivalent .NET Framework  
 Consultez `Parse` méthodes, telles que [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)