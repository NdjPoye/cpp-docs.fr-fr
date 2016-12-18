---
title: "_ITERATOR_DEBUG_LEVEL | Microsoft Docs"
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
  - "_ITERATOR_DEBUG_LEVEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ITERATOR_DEBUG_LEVEL"
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ITERATOR_DEBUG_LEVEL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La macro `_ITERATOR_DEBUG_LEVEL` \(IDL\) remplace et combine la fonctionnalité des macros [\_SECURE\_SCL](../standard-library/secure-scl.md) \(SCL\) et [\_HAS\_ITERATOR\_DEBUGGING](../standard-library/has-iterator-debugging.md) \(HID\).  
  
## Valeurs de macro  
 Les tableaux suivants résument les valeurs des macros `_SECURE_SCL` et `_HAS_ITERATOR_DEBUGGING`, et enfin comment ces valeurs sont remplacées par la macro `_ITERATOR_DEBUG_LEVEL`.  
  
 La section suivante décrit les valeurs possibles des macros SCl et HID.  
  
 SCL\=0  
 Désactive les itérateurs vérifiés.  
  
 SCL\=1  
 Active les itérateurs vérifiés.  
  
 HID\=0  
 Désactive le débogage par itération dans les versions de débogage.  
  
 HID\=1  
 Active le débogage par itération dans les versions de débogage.  HID ne peut pas être activé dans les versions releases.  
  
 Le tableau suivant décrit comment les valeurs macro IDL remplacent les valeurs de macro SCL et HID.  
  
|Mode de compilation|Nouvelle macro|Macros anciennes|Description|  
|-------------------------|--------------------|----------------------|-----------------|  
|**Débogage**||||  
||IDL\=0|SCL\=0, HID\=0|Désactive les itérateurs extraits et désactive le débogage par itération.|  
||IDL\=1|SCL\=1, HID\=0|Active les itérateurs extraits et désactive le débogage par itération.|  
||IDL\=2 \(Default\)|SCL\=\(does not apply\), HID\=1|Par défaut, active le débogage itérateur ; les itérateurs extraits ne sont pas appropriés.|  
|**Release**||||  
||IDL\=0 \(par défaut\)|SCL\=0|Par défaut, les itérateurs extraits sont désactivés.|  
||IDL\=1|SCL\=1|Active les itérateurs extraits ; le débogage par itération n'est pas nécessaire.|  
  
## Notes  
 En mode de version, une erreur est émise si vous spécifiez IDL\=2.  
  
 Les macros `_SECURE_SCL` et `_HAS_ITERATOR_DEBUGGING` prennent en charge des fonctionnalités similaires, les utilisateurs sont souvent incertains avec les macro et les macro valeurs à utiliser dans une situation donnée.  Pour résoudre ce problème, nous vous recommandons d'utiliser uniquement la macro `_ITERATOR_DEBUG_LEVEL`.  
  
## Voir aussi  
 [Bibliothèques sécurisées : bibliothèque C\+\+ standard](../standard-library/safe-libraries-cpp-standard-library.md)