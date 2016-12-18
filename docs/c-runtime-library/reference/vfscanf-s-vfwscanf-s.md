---
title: "vfscanf_s, vfwscanf_s | Microsoft Docs"
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
  - "vfscanf_s"
  - "vfwscanf_s"
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
  - "vfscanf_s"
  - "vfwscanf_s"
  - "_vftscanf_s"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 9b0133f0-9a18-4581-b24b-3b72683ad432
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vfscanf_s, vfwscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données mises en forme à partir d'un flux.  Ces versions de vfscanf, vfwscanf présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int vfscanf_s(   
   FILE *stream,  
   const char *format,  
   va_list arglist  
);  
int vfwscanf_s(   
   FILE *stream,  
   const wchar_t *format,  
   va_list arglist  
);  
  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `arglist`  
 Liste d'arguments variable.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de champs qui sont correctement convertis et assignés ; la valeur de retour n'inclut pas les champs qui ont été lus mais non assignés.  La valeur de retour 0 indique qu'aucun champ n'a été assigné.  Si une erreur se produit, ou si la fin du flux de fichiers est atteinte avant la première conversion, la valeur de retour est `EOF` pour `vfscanf_s` et `vfwscanf_s`.  
  
 Ces fonctions valident leurs paramètres.  Si `stream` est un pointeur de fichier valide ou `format` est un pointeur null, ces fonctions appelleront le gestionnaire de paramètres non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` et définissent `errno` avec la valeur `EINVAL`.  
  
## Notes  
 La fonction `vfscanf_s` lit les données à partir de la position actuelle de `stream` dans les emplacements fournis par la liste d'arguments `arglist` \(le cas échéant\).  Chaque argument de la liste doit être un pointeur vers une variable dont le type correspond à un spécificateur de type dans `format`.  `format` contrôle l'interprétation des champs d'entrée et a le même formulaire et la même fonction que l'argument `format` pour `scanf_s` ; consultez [Champs de spécification de format : fonctions scanf et wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) pour une description de `format`.  `vfwscanf_s` est une version à caractères larges de `vfscanf_s` ; l'argument de format de `vfwscanf_s` est une chaîne à caractères larges.  Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `vfscanf_s` ne prend actuellement pas en charge la saisie à partir d'un flux d'UNICODE.  
  
 La principale différence entre les fonctions plus sécurisées \(qui disposent du suffixe `_s` \) et les autres versions réside dans le fait que les fonctions plus sécurisées requièrent que la taille en caractères de chaque type de champ `c`, `C`, `s`, `S` et `[` soit passée comme argument immédiatement après la variable.  Pour plus d’informations, consultez [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) et [Spécification de largeur scanf](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Le paramètre size est de type `unsigned`, et non du type `size_t`.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vftscanf_s`|`vfscanf_s`|`vfscanf_s`|`vfwscanf_s`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`vfscanf_s`|\<stdio.h\>|  
|`vfwscanf_s`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_vfscanf_s.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses vfscanf_s to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int call_vfscanf_s(FILE * istream, char * format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vfscanf_s(istream, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main(void)  
{  
    long l;  
    float fp;  
    char s[81];  
    char c;  
  
    if (fopen_s(&stream, "vfscanf_s.out", "w+") != 0)  
    {  
        printf("The file vfscanf_s.out was not opened\n");  
    }  
    else  
    {  
        fprintf(stream, "%s %ld %f%c", "a-string",  
            65000, 3.14159, 'x');  
        // Security caution!  
        // Beware loading data from a file without confirming its size,  
        // as it may lead to a buffer overrun situation.  
  
        // Set pointer to beginning of file:  
        fseek(stream, 0L, SEEK_SET);  
  
        // Read data back from file:  
        call_vfscanf_s(stream, "%s %ld %f%c", s, _countof(s), &l, &fp, &c, 1);  
  
        // Output data read:   
        printf("%s\n", s);  
        printf("%ld\n", l);  
        printf("%f\n", fp);  
        printf("%c\n", c);  
  
        fclose(stream);  
    }  
}  
  
```  
  
  **a\-string**  
**65000**  
**3.141590**  
**x**   
## Équivalent .NET Framework  
 [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx). Voir également des méthodes `Parse`, telles que [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [vfscanf, vfwscanf](../../c-runtime-library/reference/vfscanf-vfwscanf.md)