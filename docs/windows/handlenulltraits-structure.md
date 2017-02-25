---
title: "HANDLENullTraits, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLENullTraits (structure)"
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# HANDLENullTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les caractéristiques communes d'un handle non initialisé.  
  
## Syntaxe  
  
```  
struct HANDLENullTraits;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Un synonyme de HANDLE.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[HANDLENullTraits::Close, méthode](../windows/handlenulltraits-close-method.md)|Ferme le handle spécifié.|  
|[HANDLENullTraits::GetInvalidValue, méthode](../windows/handlenulltraits-getinvalidvalue-method.md)|Représente un handle non valide.|  
  
## Hiérarchie d'héritage  
 `HANDLENullTraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)