---
title: "independent_bits_engine, classe | Microsoft Docs"
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
  - "std.tr1.independent_bits_engine"
  - "std::tr1::independent_bits_engine"
  - "tr1::independent_bits_engine"
  - "tr1.independent_bits_engine"
  - "independent_bits_engine"
  - "random/std::tr1::independent_bits_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "independent_bits_engine (classe)"
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# independent_bits_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire de nombres avec un nombre spécifié de bits en recompressant les bits des valeurs retournées par son moteur de base.  
  
## Syntaxe  
  
```  
template<class Engine, size_t W, class UIntType> class independent_bits_engine;  
```  
  
#### Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `W`  
 **Taille de mot**.  Taille, en bits, de chaque nombre généré.  **Condition préalable** : `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 Type des résultats entiers non signés.  Pour plus d'informations sur les types possibles, voir [\<random\>](../standard-library/random.md).  
  
## Membres  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Pour plus d'informations sur les membres moteurs, voir [\<random\>](../standard-library/random.md).  
  
## Notes  
 Cette classe de modèle décrit un *adaptateur de moteur* qui produit des valeurs en recompressant les bits des valeurs retournées par son moteur de base, ce qui produit des valeurs de `W` bits.  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)