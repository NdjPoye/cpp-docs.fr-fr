---
title: "ChainInterfaces::CastToUnknown, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown (méthode)"
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::CastToUnknown, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Caste le pointeur d'interface de type défini par le paramètre de modèle `I0` vers un pointeur sur IUnknown.  
  
## Syntaxe  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## Valeur de retour  
 Un pointeur vers IUnknown.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ChainInterfaces, structure](../windows/chaininterfaces-structure.md)