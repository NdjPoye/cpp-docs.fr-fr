---
title: "Implements::CastToUnknown, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Implements::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown (méthode)"
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implements::CastToUnknown, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient un pointeur vers l'interface IUnknown sous\-jacente.  
  
## Syntaxe  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## Valeur de retour  
 Cette opération réussit toujours et retourne le pointeur IUnknown.  
  
## Remarques  
 Fonction d'assistance interne.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Implements, structure](../windows/implements-structure.md)