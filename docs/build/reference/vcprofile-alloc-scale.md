---
title: "VCPROFILE_ALLOC_SCALE | Microsoft Docs"
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
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE (variable d'environnement)"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VCPROFILE_ALLOC_SCALE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifiez la quantité de mémoire allouée au stockage des données de profil.  
  
## Syntaxe  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### Paramètres  
 `scale_value`  
 Valeur d'échelle de la quantité de mémoire que vous souhaitez allouer à l'exécution des scénarios de test.  La valeur par défaut est 1.  
  
## Notes  
 Dans de rares cas, la mémoire disponible peut être insuffisante pour collecter les données de profil lors de l'exécution de scénarios de test.  Dans ces cas, vous pouvez augmenter la quantité de mémoire avec `VCPROFILE_ALLOC_SCALE`.  
  
 Si un message d'erreur s'affiche au cours d'une série de tests pour indiquer que vous ne disposez pas de suffisamment de mémoire, assignez une plus grande valeur à `VCPROFILE_ALLOC_SCALE`, jusqu'à ce que les séries de tests s'achèvent sans erreur de mémoire insuffisante.  
  
## Exemple  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## Voir aussi  
 [Variables d'environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)