---
title: "ChainInterfaces::CanCastTo, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo (méthode)"
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces::CanCastTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si l'ID d'interface spécifié peut être casté en chacune des spécialisations définies par les paramètres de modèle autres que ceux par défaut.  
  
## Syntaxe  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Paramètres  
 `riid`  
 Un ID d'interface.  
  
 `ppv`  
 Un pointeur vers le dernier ID d'interface casté avec succès.  
  
## Valeur de retour  
 `true` si toutes les opération de cast ont abouti; sinon `false`.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ChainInterfaces, structure](../windows/chaininterfaces-structure.md)