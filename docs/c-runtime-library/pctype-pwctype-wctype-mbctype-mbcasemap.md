---
title: "_pctype, _pwctype, _wctype, _mbctype, _mbcasemap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pwctype"
  - "pctype"
  - "mbctype"
  - "mbcasemap"
  - "_mbcasemap"
  - "_mbctype"
  - "_pctype"
  - "_wctype"
  - "_pcwtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctype (fonction)"
  - "_pwctype (fonction)"
  - "_pctype (fonction)"
  - "_mbctype (fonction)"
  - "wctype (fonction)"
  - "pwctype (fonction)"
  - "pctype (fonction)"
  - "mbcasemap (fonction)"
  - "mbctype (fonction)"
  - "_mbcasemap (fonction)"
ms.assetid: 7f5e1107-c43b-4b9b-b387-781e6d2373cb
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _pctype, _pwctype, _wctype, _mbctype, _mbcasemap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces variables globales contiennent des informations utilisées par les fonctions de classification des caractères.  Elles sont seulement pour l'usage interne.  
  
## Syntaxe  
  
```  
extern const unsigned short *_pctype;  
extern const wctype_t *_pwctype;  
extern const unsigned short _wctype[];  
extern unsigned char _mbctype[];  
extern unsigned char _mbcasemap[];  
```  
  
## Notes  
 Les informations dans `_pctype`, `_pwctype`, et `_wctype` sont utilisées en interne par les fonctions [isupper, \_isupper\_l, iswupper, \_iswupper\_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [islower, iswlower, \_islower\_l, \_iswlower\_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [isdigit, iswdigit, \_isdigit\_l, \_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [isxdigit, iswxdigit, \_isxdigit\_l, \_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), [isspace, iswspace, \_isspace\_l, \_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md), [isalnum, iswalnum, \_isalnum\_l, \_iswalnum\_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), [ispunct, iswpunct, \_ispunct\_l, \_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), [isgraph, iswgraph, \_isgraph\_l, \_iswgraph\_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md), et [iscntrl, iswcntrl, \_iscntrl\_l, \_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md), ainsi que des fonctions [toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md) et [tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md).  Ces fonctions peuvent être utilisées au lieu d'accéder à ces variables globales.  
  
 Les informations dans `_mbctype` et `_mbcasemap` sont utilisées en interne par [\_ismbbkalnum, \_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [\_ismbbkana, \_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), [\_ismbbkpunct, \_ismbbkpunct\_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md), [\_ismbbkprint, \_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md), [\_ismbbalpha](http://msdn.microsoft.com/fr-fr/8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0), [\_ismbbpunct, \_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [\_ismbbalnum, \_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md), [\_ismbbprint, \_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md), [\_ismbbgraph, \_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md), [\_ismbblead, \_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md), [\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), [\_ismbslead, \_ismbstrail, \_ismbslead\_l, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md), et [\_ismbslead, \_ismbstrail, \_ismbslead\_l, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md).  Utilisez ces fonctions au lieu d'accéder aux variables globales.  
  
## Configuration requise  
 Pas d'utilisation publique.  
  
## Voir aussi  
 [is, isw, routines](../c-runtime-library/is-isw-routines.md)   
 [\_\_pctype\_func](../c-runtime-library/pctype-func.md)