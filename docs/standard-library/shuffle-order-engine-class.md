---
title: "shuffle_order_engine, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "shuffle_order_engine"
  - "std.tr1.shuffle_order_engine"
  - "tr1::shuffle_order_engine"
  - "tr1.shuffle_order_engine"
  - "std::tr1::shuffle_order_engine"
  - "random/std::tr1::shuffle_order_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shuffle_order_engine (classe)"
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# shuffle_order_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire en réordonnançant les valeurs retournées à partir de son moteur de base.  
  
## Syntaxe  
  
```  
template<class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `K`  
 **Taille de table**. Nombre d'éléments dans la mémoire tampon \(table\).**Condition préalable** : `0 < K`  
  
## Membres  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random\>](../standard-library/random.md).  
  
## Notes  
 Cette classe de modèle décrit un *adaptateur de moteur* qui produit des valeurs en réordonnançant les valeurs retournées par son moteur de base. Chaque constructeur remplit la table interne avec `K` valeurs retournées par le moteur de base et un élément aléatoire est sélectionné à partir de la table quand une valeur est demandée.  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)