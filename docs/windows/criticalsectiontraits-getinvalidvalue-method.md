---
title: "CriticalSectionTraits::GetInvalidValue, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue (méthode)"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits::GetInvalidValue, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécialise un modèle CriticalSection afin que le modèle soit toujours non valide.  
  
## Syntaxe  
  
```  
inline static Type GetInvalidValue();  
```  
  
## Valeur de retour  
 Retourne toujours un pointeur vers une section critique non valide.  
  
## Remarques  
 Le modificateur *Type* est défini comme `typedef CRITICAL_SECTION* Type;`.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [CriticalSectionTraits, structure](../windows/criticalsectiontraits-structure.md)