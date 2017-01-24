---
title: "ChainInterfaces::Verify, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify (méthode)"
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::Verify, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifie que chaque interface définie par les paramètres de modèle `I0` dans `I9` hérite d'IUnknown et\/ou d'IInspectable, et que `I0` hérite de `I1` via `I9`.  
  
## Syntaxe  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## Remarques  
 Si l'opération de vérification échoue, un `static_assert` émet un message d'erreur décrivant l'échec.  
  
## Remarques  
 Les paramètres de modèle `I0` et `I1` sont requis, et les paramètres de `I2` à `I9` sont facultatifs.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ChainInterfaces, structure](../windows/chaininterfaces-structure.md)