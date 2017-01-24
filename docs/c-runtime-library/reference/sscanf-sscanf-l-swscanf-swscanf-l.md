---
title: "sscanf, _sscanf_l, swscanf, _swscanf_l | Microsoft Docs"
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
  - "swscanf"
  - "sscanf"
  - "_sscanf_l"
  - "_swscanf_l"
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
  - "_sscanf_l"
  - "_stscanf"
  - "swscanf"
  - "_stscanf_l"
  - "sscanf"
  - "_swscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sscanf_l (fonction)"
  - "_stscanf (fonction)"
  - "_stscanf_l (fonction)"
  - "_swscanf_l (fonction)"
  - "lire des données, chaînes"
  - "sscanf (fonction)"
  - "sscanf_l (fonction)"
  - "chaînes (C++), lire"
  - "chaînes (C++), lire des données à partir de"
  - "stscanf (fonction)"
  - "stscanf_l (fonction)"
  - "swscanf (fonction)"
  - "swscanf_l (fonction)"
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sscanf, _sscanf_l, swscanf, _swscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Read formatted data from a string.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).  
  
## Syntaxe  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
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
 Chaîne de contrôle de format.  Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `argument`  
 Arguments facultatifs  
  
 `locale`  
 Paramètres régionaux à utiliser  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de champs qui sont correctement convertis et assignés ; la valeur de retour n'inclut pas les champs qui ont été lus mais non assignés.  La valeur de retour 0 indique qu'aucun champ n'a été assigné.  La valeur de retour est `EOF` pour une erreur ou si la fin de la chaîne est atteinte avant la première conversion.  
  
 Si `buffer` ou `format` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et attribuent à `errno` la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `sscanf` lit les données dans le`buffer` dans l'emplacement fourni par chaque `argument`.  Chaque `argument` doit être un pointeur vers une variable dont le type correspond à un spécificateur de type dans `format`.  L'argument `format` contrôle l'interprétation des champs d'entrée et a la même forme et fonction que l'argument `format` pour la fonction `scanf`.  Si la copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
> [!IMPORTANT]
>  Lorsque vous lisez une chaîne avec `sscanf`, spécifiez toujours une largeur pour le format `%s` \(par exemple, `"%32s"` au lieu de `"%s"`\) ; sinon, l'entrée mal mise en forme peut facilement provoquer un dépassement de mémoire tampon.  
  
 `swscanf` est une version à caractères larges de `sscanf` ; les arguments de `swscanf` sont des chaînes à caractères larges.  `sscanf` ne gère pas les caractères hexadécimaux multi octets.  `swscanf` ne gère pas les caractères pleine chasse hexadécimaux Unicode ou de « zone de compatibilité ».  Sinon, `swscanf` et `sscanf` se comportent de la même façon.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`sscanf`, `_sscanf_l`|\<stdio.h\>|  
|`swscanf`, `_swscanf_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
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
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)