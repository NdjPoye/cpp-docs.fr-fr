---
title: "Classification d&#39;octets | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types.bytes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "routines de classifications d'octets"
  - "octets, tester"
  - "page de codes 932"
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Classification d&#39;octets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chacune de ces routines teste un octets spécifié d'un caractères multioctets pour la satisfaction d'une condition.  La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  
  
> [!NOTE]
>  \(Par définition, le jeu de caractères ASCII de 0 à 127 est un sous\-ensemble de tous les jeux de caractères multioctets.  Par exemple, le jeu de caractères japonais katakana de incluent les caractères ASCII ainsi que ASCII.  
  
 Les constantes prédéfinies dans le tableau suivant sont définies dans CTYPE.H.  
  
### Routines de caractères multi\-octets d'Octet\- classification  
  
|Routine|Condition de test de l'octet.|Équivalent de .NET Framework|  
|-------------|-----------------------------------|----------------------------------|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|KPI ; le résultat de test dépend de la valeur de catégorie de `LC_CTYPE` les paramètres régionaux actuels|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbalnum, \_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum &#124;&#124; _ismbbkalnum`|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbalpha, \_ismbbalpha\_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|`isalpha &#124;&#124; _ismbbkalnum`|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbgraph, \_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Même que `_ismbbprint`, mais `_ismbbgraph` n'inclut pas l'espace \(0x20\).|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbkalnum, \_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Symbole de texte non\-ASCII autre que la ponctuation.  Par exemple, dans la page de codes 932 uniquement, tests `_ismbbkalnum` pour les alphanumériques Katakana.|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbkana, \_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana 0xA1 \(– 0xDF\), page de codes 932 uniquement|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbkprint, \_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Texte non ASCII ou symboles de ponctuation non\-ASCII.  Par exemple, dans la page de codes 932 uniquement, `_ismbbkprint` teste les Katakana alphanumériques ou la ponctuation Katakana \(plage : 0xA1 – 0xDF\).|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbkpunct, \_ismbbkpunct\_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Ponctuation non\-ASCIIE.  Par exemple, dans la page de codes 932 uniquement, tests `_ismbbkpunct` pour les alphanumériques Katakana.|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbblead, \_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Premier octet de caractères multi\-octets.  Par exemple, dans la page de codes 932 uniquement, les plages valides sont 0x81 – 0x9F, 0xE0 – 0xFC.|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbprint, \_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint &#124;&#124; _ismbbkprint. ismbbprint` comprend l'espace \(0x20\)|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbpunct, \_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct &#124;&#124; _ismbbkpunct`|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Deuxième octet de caractères multi\-octets.  Par exemple, dans la page de codes 932 uniquement, les plages valides sont 0x40 – 0x7E, 0x80 – 0xEC.|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_ismbslead, \_ismbslead\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Indicateur de performance clé \(dans le contexte de chaîne\)|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[ismbstrail, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Octets de fin \(dans le contexte de chaîne\)|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_mbbtype, \_mbbtype\_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Type de retour d'octets sur l'octet précédent|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[\_mbsbtype, \_mbsbtype\_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Type de retour d'octets dans la chaîne|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Suit l'état d'une conversion de caractères multi\-octets.|Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).|  
  
 La macro d'`MB_LEN_MAX`, définie dans LIMITS.H, développe la longueur maximale en octets que tous les caractères multioctets peut avoir.  `MB_CUR_MAX`, défini dans STDLIB.H, développe la longueur maximale en octets de toutes les caractères multioctets dans les paramètres régionaux actuels.  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)