---
title: "is, isw, routines | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "isw"
  - "is"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "is (routines)"
  - "isw (routines)"
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is, isw, routines
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[isalnum, iswalnum, \_isalnum\_l, \_iswalnum\_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md)|[isgraph, iswgraph, \_isgraph\_l, \_iswgraph\_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)|  
|[isalpha, iswalpha, \_isalpha\_l, \_iswalpha\_l](../c-runtime-library/reference/isalpha-iswalpha-isalpha-l-iswalpha-l.md)|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|  
|[isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, \_islower\_l, \_iswlower\_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)|  
|[isblank, iswblank, \_isblank\_l, \_iswblank\_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, \_isprint\_l, \_iswprint\_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|  
|[iscntrl, iswcntrl, \_iscntrl\_l, \_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, \_ispunct\_l, \_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|  
|[iscsym, iscsymf, \_\_iscsym, \_\_iswcsym, \_\_iscsymf, \_\_iswcsymf, \_iscsym\_l, \_iswcsym\_l, \_iscsymf\_l, \_iswcsymf\_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, \_isspace\_l, \_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|  
|[\_isctype, iswctype, \_isctype\_l, \_iswctype\_l](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|[isupper, \_isupper\_l, iswupper, \_iswupper\_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)|  
|[isdigit, iswdigit, \_isdigit\_l, \_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, \_isxdigit\_l, \_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|  
  
## Notes  
 Ces routines testent des caractères pour des conditions spécifiés.  
  
 Les routines **is** produisent des résultats significatifs pour tout argument entier de – 1 \(`EOF`\) à **UCHAR\_MAX** \(0xFF\), inclus.  Le type d'argument attendu est `int`.  
  
> [!CAUTION]
>  Pour les routines **is**, le passage d'un argument de type `char` peut générer des résultats imprévisibles.  Un caractère à octet unique SBCS ou MBCS de type `char` avec une valeur supérieure à 0x7F est négatif.  Si `char` est passé, le compilateur peut convertir la valeur en un `int` signé ou un **long** signé.  Cette valeur peut être étendue à d'autres signes par le compilateur, en produisant des résultats inattendus.  
  
 Les routines **isw** produisent des résultats significatifs pour toute valeur entière de – 1 \(**WEOF**\) à 0xFFFF, inclus.  Le type de données **wint\_t** est défini dans WCHAR.H en tant que **short non signé**; il peut contenir n'importe quel caractère large ou la valeur du caractère large de fin de fichier \(**WEOF**\).  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe **\_l** utilisent les paramètres régionaux courants pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe **\_l** sont identiques, sauf qu'elles utilisent le paramètre régional passé à la place.  
  
 Dans les paramètres régionaux « C », les conditions de test pour les routines **is** sont les suivantes :  
  
 `isalnum`  
 Chiffre alphanumérique \(A – Z, a et z, ou 0 – 9\).  
  
 `isalpha`  
 Alphabétique \(A – Z ou a à z\).  
  
 `__isascii`  
 Caractère ASCII \(0x00 – 0x7F\).  
  
 `isblank`  
 Tabulation horizontale ou espace \(0x09 ou 0x20\).  
  
 `iscntrl`  
 Caractère de contrôle \(0x00 – 0x1F ou 0x7F\).  
  
 `__iscsym`  
 Lettre, trait de soulignement, ou chiffre.  
  
 `__iscsymf`  
 Lettre ou trait de soulignement.  
  
 **isdigit**  
 Chiffre décimal \(0 – 9\).  
  
 `isgraph`  
 Caractère imprimable sauf l'espace \( \).  
  
 `islower`  
 Lettre minuscule \(a – z\).  
  
 `isprint`  
 Caractère imprimable notamment l'espace \(0x20 – 0x7E\).  
  
 `ispunct`  
 Caractère de ponctuation.  
  
 `isspace`  
 Caractère espace blanc \(0x09 – 0x0D ou 0x20\).  
  
 `isupper`  
 Lettres majuscules \(A – Z\).  
  
 `isxdigit`  
 Chiffre hexadécimal \(A – F, a – f, ou 0 – 9\).  
  
 Pour les routines **isw**, le résultat du test pour les conditions spécifiées est indépendant des paramètres régionaux.  Les conditions de test pour les fonctions **isw** sont les suivantes :  
  
 `iswalnum`  
 `iswalpha` ou `iswdigit`.  
  
 `iswalpha`  
 Tout caractère large qui fait partie d'un ensemble défini par implémentation pour lequel aucun de `iswcntrl`, en `iswdigit`, `iswpunct`, ou `iswspace` n'est différent de zéro.  `iswalpha` retourne une valeur différente de zéro uniquement pour des caractères larges pour lesquels `iswupper` ou `iswlower` est différent de zéro.  
  
 `iswascii`  
 Représentation en caractère larges du caractère ASCII \(0x0000 – 0x007F\).  
  
 `iswblank`  
 Caractère large qui correspond au caractère d'espace standard ou est un ensemble défini par implémentation de caractères larges pour lesquels `iswalnum` est faux.  Les caractères blancs standard sont l'espace \(L" "\) et la tabulation horizontale \(L'\\t'\).  
  
 `iswcntrl`  
 Caractère large de contrôle.  
  
 **\_\_iswcsym**  
 Tout caractère large pour lequel **isalnum** est vrai, ou le caractère « \_ ».  
  
 **\_\_iswcsymf**  
 Tout caractère large pour lequel `iswalpha` est vrai, ou le caractère « \_ ».  
  
 `iswctype`  
 Le caractère possède la propriété spécifiée par l'argument `desc`.  Pour chaque valeur valide de l'argument `desc` de `iswctype`, il existe une routine de classification de caractères larges équivalente, comme indiqué dans le tableau suivant :  
  
 **Equivalence of iswctype\(**   
 ***c, desc* \) à d'autres routines de test isw**  
  
|Valeur de l'argument *desc*|équivalent de iswctype \( *c, desc* \)|  
|---------------------------------|--------------------------------------------|  
|**\_ALPHA**|**iswalpha\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT**|**iswalnum\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_CONTROL**|**iswcntrl\(** `c` **\)**|  
|**\_DIGIT**|**iswdigit\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswgraph\(** `c` **\)**|  
|**\_LOWER**|**iswlower\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_BLANK** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswprint\(** `c` **\)**|  
|**\_PUNCT**|**iswpunct\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_SPACE**|**iswspace\(** `c` **\)**|  
|**\_UPPER**|**iswupper\(** `c` **\)**|  
|**\_HEX**|**iswxdigit\(** `c` **\)**|  
  
 `iswdigit`  
 Caractère large correspondant à un caractère de chiffre décimal.  
  
 `iswgraph`  
 Caractère large imprimable à l'exception du caractère large d'space \(L' '\).  
  
 `iswlower`  
 Lettre minuscule, ou l'un des ensembles défini par implémentation de caractères larges pour lesquels aucun de `iswcntrl`, `iswdigit`, `iswpunct`, ou `iswspace` n'est différent de zéro.  `iswlower` retourne une valeur différente de zéro uniquement pour les caractères larges qui correspondent à des lettres minuscules.  
  
 `iswprint`  
 Caractère large imprimable y compris le caractère large d'space \(L' '\).  
  
 `iswpunct`  
 Caractère large imprimable qui n'est ni un caractère large d'espace \(L' '\) ni un caractère large pour lequel `iswalnum` est différent de zéro.  
  
 `iswspace`  
 Caractère large qui correspond au caractère d'espace blanc standard ou est un ensemble défini par implémentation de caractères larges pour lesquels `iswalnum` est faux.  Les espaces blancs standard sont : l'espace \(L' '\), chargement de page \(L'\\f'\), saut de ligne \(L'\\n'\), retour chariot \(L'\\r'\), tabulation horizontale \(L'\\t'\), et vertical \(L'\\v'\).  
  
 `iswupper`  
 Caractère large qui est en majuscules ou est un ensemble défini par implémentation de caractères larges pour lesquels aucun de `iswcntrl`, `iswdigit`, `iswpunct`, ou `iswspace` n'est différent de zéro.  `iswupper` retourne une valeur différente de zéro uniquement pour les caractères larges qui correspondent à des lettres majuscules.  
  
 `iswxdigit`  
 Caractère large qui correspond à un caractère de chiffre hexadécimal.  
  
## Exemple  
  
```  
// crt_isfam.c  
/* This program tests all characters between 0x0  
 * and 0x7F, then displays each character with abbreviations  
 * for the character-type codes that apply.  
 */  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   for( ch = 0; ch <= 0x7F; ch++ )  
   {  
      printf( "%.2x  ", ch );  
      printf( " %c", isprint( ch )  ? ch   : ' ' );  
      printf( "%4s", isalnum( ch )  ? "AN" : "" );  
      printf( "%3s", isalpha( ch )  ? "A"  : "" );  
      printf( "%3s", __isascii( ch )  ? "AS" : "" );  
      printf( "%3s", iscntrl( ch )  ? "C"  : "" );  
      printf( "%3s", __iscsym( ch )  ? "CS "  : "" );  
      printf( "%3s", __iscsymf( ch )  ? "CSF"  : "" );  
      printf( "%3s", isdigit( ch )  ? "D"  : "" );  
      printf( "%3s", isgraph( ch )  ? "G"  : "" );  
      printf( "%3s", islower( ch )  ? "L"  : "" );  
      printf( "%3s", ispunct( ch )  ? "PU" : "" );  
      printf( "%3s", isspace( ch )  ? "S"  : "" );  
      printf( "%3s", isprint( ch )  ? "PR" : "" );  
      printf( "%3s", isupper( ch )  ? "U"  : "" );  
      printf( "%3s", isxdigit( ch ) ? "X"  : "" );  
      printf( ".\n" );  
   }  
}  
```  
  
## Sortie  
  
```  
00            AS  C                              .  
01            AS  C                              .  
02            AS  C                              .  
03            AS  C                              .  
04            AS  C                              .  
05            AS  C                              .  
06            AS  C                              .  
07            AS  C                              .  
08            AS  C                              .  
09            AS  C                    S         .  
0a            AS  C                    S         .  
0b            AS  C                    S         .  
0c            AS  C                    S         .  
0d            AS  C                    S         .  
0e            AS  C                              .  
0f            AS  C                              .  
10            AS  C                              .  
11            AS  C                              .  
12            AS  C                              .  
13            AS  C                              .  
14            AS  C                              .  
15            AS  C                              .  
16            AS  C                              .  
17            AS  C                              .  
18            AS  C                              .  
19            AS  C                              .  
1a            AS  C                              .  
1b            AS  C                              .  
1c            AS  C                              .  
1d            AS  C                              .  
1e            AS  C                              .  
1f            AS  C                              .  
20            AS                       S PR      .  
21   !        AS              G    PU    PR      .  
22   "        AS              G    PU    PR      .  
23   #        AS              G    PU    PR      .  
24   $        AS              G    PU    PR      .  
25   %        AS              G    PU    PR      .  
26   &        AS              G    PU    PR      .  
27   '        AS              G    PU    PR      .  
28   (        AS              G    PU    PR      .  
29   )        AS              G    PU    PR      .  
2a   *        AS              G    PU    PR      .  
2b   +        AS              G    PU    PR      .  
2c   ,        AS              G    PU    PR      .  
2d   -        AS              G    PU    PR      .  
2e   .        AS              G    PU    PR      .  
2f   /        AS              G    PU    PR      .  
30   0  AN    AS   CS      D  G          PR     X.  
31   1  AN    AS   CS      D  G          PR     X.  
32   2  AN    AS   CS      D  G          PR     X.  
33   3  AN    AS   CS      D  G          PR     X.  
34   4  AN    AS   CS      D  G          PR     X.  
35   5  AN    AS   CS      D  G          PR     X.  
36   6  AN    AS   CS      D  G          PR     X.  
37   7  AN    AS   CS      D  G          PR     X.  
38   8  AN    AS   CS      D  G          PR     X.  
39   9  AN    AS   CS      D  G          PR     X.  
3a   :        AS              G    PU    PR      .  
3b   ;        AS              G    PU    PR      .  
3c   <        AS              G    PU    PR      .  
3d   =        AS              G    PU    PR      .  
3e   >        AS              G    PU    PR      .  
3f   ?        AS              G    PU    PR      .  
40   @        AS              G    PU    PR      .  
41   A  AN  A AS   CS CSF     G          PR  U  X.  
42   B  AN  A AS   CS CSF     G          PR  U  X.  
43   C  AN  A AS   CS CSF     G          PR  U  X.  
44   D  AN  A AS   CS CSF     G          PR  U  X.  
45   E  AN  A AS   CS CSF     G          PR  U  X.  
46   F  AN  A AS   CS CSF     G          PR  U  X.  
47   G  AN  A AS   CS CSF     G          PR  U   .  
48   H  AN  A AS   CS CSF     G          PR  U   .  
49   I  AN  A AS   CS CSF     G          PR  U   .  
4a   J  AN  A AS   CS CSF     G          PR  U   .  
4b   K  AN  A AS   CS CSF     G          PR  U   .  
4c   L  AN  A AS   CS CSF     G          PR  U   .  
4d   M  AN  A AS   CS CSF     G          PR  U   .  
4e   N  AN  A AS   CS CSF     G          PR  U   .  
4f   O  AN  A AS   CS CSF     G          PR  U   .  
50   P  AN  A AS   CS CSF     G          PR  U   .  
51   Q  AN  A AS   CS CSF     G          PR  U   .  
52   R  AN  A AS   CS CSF     G          PR  U   .  
53   S  AN  A AS   CS CSF     G          PR  U   .  
54   T  AN  A AS   CS CSF     G          PR  U   .  
55   U  AN  A AS   CS CSF     G          PR  U   .  
56   V  AN  A AS   CS CSF     G          PR  U   .  
57   W  AN  A AS   CS CSF     G          PR  U   .  
58   X  AN  A AS   CS CSF     G          PR  U   .  
59   Y  AN  A AS   CS CSF     G          PR  U   .  
5a   Z  AN  A AS   CS CSF     G          PR  U   .  
5b   [        AS              G    PU    PR      .  
5c   \        AS              G    PU    PR      .  
5d   ]        AS              G    PU    PR      .  
5e   ^        AS              G    PU    PR      .  
5f   _        AS   CS CSF     G    PU    PR      .  
60   `        AS              G    PU    PR      .  
61   a  AN  A AS   CS CSF     G  L       PR     X.  
62   b  AN  A AS   CS CSF     G  L       PR     X.  
63   c  AN  A AS   CS CSF     G  L       PR     X.  
64   d  AN  A AS   CS CSF     G  L       PR     X.  
65   e  AN  A AS   CS CSF     G  L       PR     X.  
66   f  AN  A AS   CS CSF     G  L       PR     X.  
67   g  AN  A AS   CS CSF     G  L       PR      .  
68   h  AN  A AS   CS CSF     G  L       PR      .  
69   i  AN  A AS   CS CSF     G  L       PR      .  
6a   j  AN  A AS   CS CSF     G  L       PR      .  
6b   k  AN  A AS   CS CSF     G  L       PR      .  
6c   l  AN  A AS   CS CSF     G  L       PR      .  
6d   m  AN  A AS   CS CSF     G  L       PR      .  
6e   n  AN  A AS   CS CSF     G  L       PR      .  
6f   o  AN  A AS   CS CSF     G  L       PR      .  
70   p  AN  A AS   CS CSF     G  L       PR      .  
71   q  AN  A AS   CS CSF     G  L       PR      .  
72   r  AN  A AS   CS CSF     G  L       PR      .  
73   s  AN  A AS   CS CSF     G  L       PR      .  
74   t  AN  A AS   CS CSF     G  L       PR      .  
75   u  AN  A AS   CS CSF     G  L       PR      .  
76   v  AN  A AS   CS CSF     G  L       PR      .  
77   w  AN  A AS   CS CSF     G  L       PR      .  
78   x  AN  A AS   CS CSF     G  L       PR      .  
79   y  AN  A AS   CS CSF     G  L       PR      .  
7a   z  AN  A AS   CS CSF     G  L       PR      .  
7b   {        AS              G    PU    PR      .  
7c   |        AS              G    PU    PR      .  
7d   }        AS              G    PU    PR      .  
7e   ~        AS              G    PU    PR      .  
7f            AS  C                              .  
```  
  
## Voir aussi  
 [Classifications des caractères](../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Interprétation des séquences de caractères multioctets](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [to, fonctions](../c-runtime-library/to-functions.md)