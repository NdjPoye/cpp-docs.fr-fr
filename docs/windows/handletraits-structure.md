---
title: "HANDLETraits, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLETraits (structure)"
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# HANDLETraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les caractéristiques communes d'un handle.  
  
## Syntaxe  
  
```  
struct HANDLETraits;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Type`|Un synonyme de HANDLE.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[HANDLETraits::Close, méthode](../windows/handletraits-close-method.md)|Ferme le handle spécifié.|  
|[HANDLETraits::GetInvalidValue, méthode](../windows/handletraits-getinvalidvalue-method.md)|Représente un handle non valide.|  
  
## Hiérarchie d'héritage  
 `HANDLETraits`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::HandleTraits, espace de noms](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)