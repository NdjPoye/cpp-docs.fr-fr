---
title: "high_property_prefixes | Microsoft Docs"
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
  - "high_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "high_property_prefixes (attribut)"
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# high_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie d'autres préfixes pour trois méthodes de propriété.  
  
## Syntaxe  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### Paramètres  
 `GetPrefix`  
 Préfixe à utiliser pour les méthodes **propget**.  
  
 `PutPrefix`  
 Préfixe à utiliser pour les méthodes **propput**.  
  
 `PutRefPrefix`  
 Préfixe à utiliser pour les méthodes **propputref**.  
  
## Notes  
 Par défaut, les méthodes de gestion d'erreurs de niveau supérieur **propget**, **propput** et **propputref** sont exposées par des fonctions membres nommées avec les préfixes **Get**, `Put`, et **PutRef**, respectivement.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)