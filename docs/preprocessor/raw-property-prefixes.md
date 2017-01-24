---
title: "raw_property_prefixes | Microsoft Docs"
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
  - "raw_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_property_prefixes (attribut)"
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie d'autres préfixes pour trois méthodes de propriété.  
  
## Syntaxe  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### Paramètres  
 `GetPrefix`  
 Préfixe à utiliser pour les méthodes **propget**.  
  
 `PutPrefix`  
 Préfixe à utiliser pour les méthodes **propput**.  
  
 `PutRefPrefix`  
 Préfixe à utiliser pour les méthodes **propputref**.  
  
## Notes  
 Par défaut, les méthodes de bas niveau **propget**, **propput** et **propputref** sont exposées par les fonctions membres nommées respectivement avec les préfixes **get\_**, **put\_** et **putref\_**.  Ces préfixes sont compatibles avec les noms utilisés dans les fichiers d'en\-tête générés par MIDL.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)