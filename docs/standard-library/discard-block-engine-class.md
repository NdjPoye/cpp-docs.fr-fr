---
title: "discard_block_engine, classe | Microsoft Docs"
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
  - "tr1.discard_block_engine"
  - "std.tr1.discard_block_engine"
  - "std::tr1::discard_block_engine"
  - "random/std::tr1::discard_block_engine"
  - "discard_block_engine"
  - "tr1::discard_block_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discard_block_engine (classe)"
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# discard_block_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire en ignorant les valeurs retournées par son moteur de base.  
  
## Syntaxe  
  
```  
template<class Engine, size_t P, size_t R> class discard_block_engine;  
```  
  
#### Paramètres  
 `Engine`  
 Type de moteur de base.  
  
 `P`  
 **Taille de bloc**.  Nombre de valeurs dans chaque bloc.  
  
 `R`  
 **Bloc utilisé**.  Nombre de valeurs dans chaque bloc qui sont utilisées.  Les autres sont ignorées \(`P` \- `R`\).  **Condition préalable** : `0 < R ≤ P`  
  
## Membres  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 Pour plus d'informations sur les membres moteurs, voir [\<random\>](../standard-library/random.md).  
  
## Notes  
 Cette classe de modèle décrit un adaptateur de moteur qui produit des valeurs en écartant certaines des valeurs retournées par son moteur de base.  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)