---
title: "_daylight, _dstbias, _timezone, and _tzname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fuseaux horaires"
  - "réglage de l'heure"
  - "variables de fuseau horaire"
  - "_tzname (fonction)"
  - "_daylight (fonction)"
  - "_timezone (fonction)"
  - "daylight (fonction)"
  - "réglage de l'heure locale"
  - "timezone (fonction)"
  - "tzname (fonction)"
  - "variables de fuseau horaire"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _daylight, _dstbias, _timezone, and _tzname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_daylight`, `_dstbias`, `_timezone`, et `_tzname` sont utilisés dans certaines routines de date et d'heure pour effectuer des ajustements heure locale.  Ces variables globales sont déconseillées face aux versions plus sécurisées, qui doivent être utilisées à la place des variables globales.  
  
|Variable globale.|Équivalent fonctionnel|  
|-----------------------|----------------------------|  
|`_daylight`|[\_get\_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[\_get\_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[\_get\_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Elles sont déclarées dans Time.h comme suit.  
  
## Syntaxe  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## Notes  
 Lors d'un appel à `_ftime`, `localtime`, ou `_tzset`, les valeurs de`_daylight`, `_dstbias`, d'`_timezone`, et `_tzname` sont déterminés à partir de la valeur de la variable d'environnement `TZ`.  Si vous ne définissez pas explicitement la valeur de`TZ`, `_tzname[0]` et `_tzname[1]` contiennent les paramètres par défaut « PST » et « PDT »respectivement.  La fonction de mainpulation du temps \([\_tzset](../c-runtime-library/reference/tzset.md), [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md), et [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)\)sont utilisées pour définir les valeurs de`_daylight`, `_dstbias` et de`_timezone` en interrogeant le système d'exploitation pour définir les valeurs par défaut de chaque variable.  Les valeurs de variable globale de fuseau horaire sont répertoriées dans le tableau suivant.  
  
|Variable|Valeur|  
|--------------|------------|  
|`_daylight`|Une valeur différente de zéro si la zone \(DST\) de l'heure d'été est spécifiée dans `TZ` ou déterminée à partir du système d'exploitation ; sinon, 0.  La valeur par défaut est 1.|  
|`_dstbias`|décalage de l'heure d'été.|  
|`_timezone`|Différence en secondes entre le temps universel coordonné et l'heure locale.  La valeur par défaut est 28,800.|  
|`_tzname[0]`|Nom du fuseau horaire dérivé de la variable d'environnement `TZ`.  La valeur par défaut est "PST".|  
|`_tzname[1]`|Nom du fuseau horaire dérivé de la variable d'environnement `TZ`.  La valeur par défaut est « PDT » \(heure d'été au Pacifique\).|  
  
## Voir aussi  
 [Variables globales](../c-runtime-library/global-variables.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)