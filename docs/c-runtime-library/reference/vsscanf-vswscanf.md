---
title: "vsscanf, vswscanf | Microsoft Docs"
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
  - "vsscanf"
  - "vswscanf"
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
  - "_vstscanf"
  - "vsscanf"
  - "vswscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsscanf (fonction)"
  - "vswscanf (fonction)"
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
caps.latest.revision: 9
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vsscanf, vswscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données mises en forme à partir d'une chaîne.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md).  
  
## Syntaxe  
  
```  
int vsscanf(  
   const char *buffer,  
   const char *format,  
   va_list arglist  
);  
int vswscanf(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### Paramètres  
 `buffer`  
 Données stockées  
  
 `format`  
 Chaîne de contrôle de format.  Pour plus d'informations, consultez [Champs de spécification de format : fonctions scanf et wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `arglist`  
 Liste d'arguments variable.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de champs qui sont correctement convertis et assignés ; la valeur de retour n'inclut pas les champs qui ont été lus mais non assignés.  La valeur de retour 0 indique qu'aucun champ n'a été assigné.  La valeur de retour est `EOF` pour une erreur ou si la fin de la chaîne est atteinte avant la première conversion.  
  
 Si `buffer` ou `format` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et attribuent à `errno` la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `vsscanf` lit les données de `buffer` dans les emplacements fournis par chaque argument de la liste d'arguments `arglist`.  Chaque argument de la liste doit être un pointeur vers une variable dont le type correspond à un spécificateur de type dans `format`.  L'argument `format` contrôle l'interprétation des champs d'entrée et a la même forme et fonction que l'argument `format` pour la fonction `scanf`.  Si la copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
> [!IMPORTANT]
>  Lorsque vous utilisez `vsscanf` pour lire une chaîne, spécifiez toujours une largeur du format de `%s` \(par exemple, `"%32s"` au lieu de `"%s"`\) ; sinon, l'entrée mal mise en forme peut provoquer un dépassement de mémoire tampon.  
  
 `vswscanf` est une version à caractères larges de `vsscanf` ; les arguments vers `vswscanf` sont des chaînes à caractères larges.  `vsscanf` ne gère pas les caractères hexadécimaux multi octets.  `vswscanf` ne gère pas les caractères pleine chasse hexadécimaux Unicode ou de « zone de compatibilité ».  Sinon, `vswscanf` et `vsscanf` se comportent de la même façon.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_vstscanf`|`vsscanf`|`vsscanf`|`vswscanf`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`vsscanf`|\<stdio.h\>|  
|`vswscanf`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_vsscanf.c  
// compile with: /W3  
// This program uses vsscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vsscanf(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf(tokenstring, "%80s", s);  
    call_vsscanf(tokenstring, "%c", &c);  
    call_vsscanf(tokenstring, "%d", &i);  
    call_vsscanf(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
  **Chaîne    \= 15**  
**Caractère \= 1**  
**Entier :  \= 15**  
**Réel :     \= 15.000000**   
## Équivalent .NET Framework  
 Voir également les méthodes `Parse`, telles que [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)