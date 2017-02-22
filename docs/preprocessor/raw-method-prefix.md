---
title: "raw_method_prefix | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_method_prefix"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_method_prefix (attribut)"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# raw_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie un préfixe différent pour éviter les collisions de noms.  
  
## Syntaxe  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### Paramètres  
 `Prefix`  
 Le préfixe à utiliser.  
  
## Notes  
 Les propriétés et les méthodes de bas niveau sont exposées par les fonctions membres nommées avec un préfixe par défaut **raw\_** pour éviter des conflits de noms avec les fonctions membres de gestion des erreurs de niveau supérieur.  
  
> [!NOTE]
>  Les effets de l'attribut `raw_method_prefix` ne sont pas modifiés par la présence de l'attribut [raw\_interfaces\_only](#_predir_raw_interfaces_only).  `raw_method_prefix` a toujours la priorité sur `raw_interfaces_only` pour spécifier un préfixe.  Si les deux attributs sont utilisés dans la même instruction `#import`, le préfixe spécifié par l'attribut `raw_method_prefix` est utilisé.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)