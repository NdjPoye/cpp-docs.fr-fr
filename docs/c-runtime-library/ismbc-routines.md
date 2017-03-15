---
title: "_ismbc, routines | Microsoft Docs"
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
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbc (routines)"
  - "ismbc (routines)"
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbc, routines
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque routine **\_ismbc** teste un caractère multi\-octets donné `c` pour une condition particulière.  
  
|||  
|-|-|  
|[\_ismbcalnum, \_ismbcalnum\_l, \_ismbcalpha, \_ismbcalpha\_l, \_ismbcdigit, \_ismbcdigit\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|[\_ismbcl0, \_ismbcl0\_l, \_ismbcl1, \_ismbcl1\_l, \_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|  
|[\_ismbcgraph, \_ismbcgraph\_l, \_ismbcprint, \_ismbcprint\_l, \_ismbcpunct, \_ismbcpunct\_l, \_ismbcblank, \_ismbcblank\_l, \_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[\_ismbclegal, \_ismbclegal\_l, \_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|  
|[\_ismbchira, \_ismbchira\_l, \_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[\_ismbclower, \_ismbclower\_l, \_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|  
  
## Notes  
 Le résultat des tests de chaque routine **\_ismbc** dépend de la page de codes multi\-octets en vigueur.  Les pages de codes multi\-octets ont les lettres codées sur un octet.  Par défaut, la page de codes multi\-octets est définie dans la page de codes ANSI de système par défaut obtenue du système d'exploitation au démarrage du programme.  Il est possible d'interroger ou modifier la page de codes multi\-octets en service avec [\_getmbcp](../c-runtime-library/reference/getmbcp.md) ou [\_setmbcp](../c-runtime-library/reference/setmbcp.md), respectivement.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [](../c-runtime-library/reference/setlocale-wsetlocale.md "setlocale, _wsetlocale") pour plus d'informations.  Les versions de ces fonctions sans le suffixe **\_l** utilisent les paramètres régionaux courants pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe **\_l** sont identiques, sauf qu'elles utilisent le paramètre régional passé à la place.  
  
|Routine|Condition de test|Exemple de page de codes 932|  
|-------------|-----------------------|----------------------------------|  
|[\_ismbcalnum, \_ismbcalnum\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Caractère alphanumérique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une lettre ASCII en anglais : Afficher des exemples pour `_ismbcdigit` et `_ismbcalpha`.|  
|[\_ismbcalpha, \_ismbcalpha\_](../c-runtime-library/reference/ismbcalnum-functions.md)|Alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une lettre en anglais ASCII : Voir exemples pour `_ismbcupper` et `_ismbclower`; ou une lettre de katakana: 0xA6\<\=`c`\<\=0xDF.\+|  
|[\_ismbcdigit, \_ismbcdigit\_l](../c-runtime-library/reference/ismbcalnum-functions.md)|Chiffre|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un chiffre ASCII : 0x30\=\<`c`\<\=0x39.|  
|[\_ismbcgraph, \_ismbcgraph\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Graphique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un caractère ASCII ou d'un Katakana imprimable sauf un espace blanc \( \).  Voir des exemples pour `_ismbcdigit`, `_ismbcalpha` et `_ismbcpunct`.|  
|[\_ismbclegal, \_ismbclegal\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Caractère multi\-octets valide|Retourne une valeur différente de zéro si et seulement si le premier octet de `c` est dans les limites 0x81 – 0x9F ou 0xE0 – 0xFC, alors que le deuxième octet est dans les limites 0x40 – 0x7E ou 0x80 \- FC.|  
|[\_ismbclower, \_ismbclower\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Lettre minuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une minuscule ASCII en anglais : 0x61\=\<`c`\<\=0x7A.|  
|[\_ismbcprint, \_ismbcprint\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Imprimable|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet de tout ASCII ou caractère imprimable Katakana y compris un espace blanc \( \) : Afficher des exemples pour `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha`, et `_ismbcpunct`.|  
|[\_ismbcpunct, \_ismbcpunct\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Ponctuation|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un caractère de ponctuation ASCII ou Katakana.|  
|[\_ismbcblank, \_ismbcblank\_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Espace ou tabulation horizontale|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'un espace ou un caractère de tabulation horizontale : `c`\=0x20 ou `c`\=0x09.|  
|[\_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Whitespace|Retourne une valeur différente de zéro si et seulement si `c` est un espace blanc : `c`\=0x20 ou 0x09\=\<`c`\<\=0x0D.|  
|[\_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Symbole multi\-octets|Retourne une valeur différente de zéro si et seulement si 0x8141\<\=`c`\<\=0x81AC.|  
|[\_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Majuscule alphabétique|Retourne une valeur différente de zéro si et seulement si `c` est une représentation codée sur un octet d'une majuscule ASCII en anglais : 0x41\=\<`c`\<\=0x5A.|  
  
 **Détail de la page de codes 932**  
  
 Les routines suivantes sont spécifiques à la page de codes 932.  
  
|Routine|Condition de test \(page de codes 932 uniquement\)|  
|-------------|--------------------------------------------------------|  
|[\_ismbchira, \_ismbchira\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Hiragana de Deux octets : 0x829F\=\<`c`\<\=0x82F1.|  
|[\_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Katakana de deux octets : 0x8340\=\<`c`\<\=0x8396.|  
|[\_ismbcl0, \_ismbcl0\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|Non kanji de JIS : 0x8140\=\<`c`\<\=0x889E.|  
|[\_ismbcl1, \_ismbcl1\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS : niveau 1: 0x889F\=\<`c`\<\=0x9872.|  
|[\_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS niveau\-2 : 0x989F\=\<`c`\<\=0xEA9E.|  
  
 `_ismbcl0`, `_ismbcl1`, et `_ismbcl2` vérifient que la valeur spécifiée `c` correspond aux conditions de test décrites dans le tableau précédent, mais ne vérifient pas que `c` est un caractère multi\-octets valide.  Si l'octet inférieur est dans des plages 0x00 – 0x3F, 0x7F, ou 0xFD – 0xFF, ces fonctions retournent une valeur différente de zéro, indiquant que le caractère remplit la condition de test.  Utilisez [\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) pour tester si le caractère multi\-octets est défini.  
  
 **Détail de la page de codes 932**  
  
## Voir aussi  
 [Classifications des caractères](../c-runtime-library/character-classification.md)   
 [is, isw, routines](../c-runtime-library/is-isw-routines.md)   
 [\_ismbb, routines](../c-runtime-library/ismbb-routines.md)