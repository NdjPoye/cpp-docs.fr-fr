---
title: "BoolStruct, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::BoolStruct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BoolStruct (structure)"
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# BoolStruct, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
struct BoolStruct;  
```  
  
## Notes  
 La structure BoolStruct définit si un ComPtr gère la durée de vie d'un objet d'une interface.  BoolStruct est utilisé en interne par l'opérateur [BoolType\(\)](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md).  
  
## Membres  
  
### Données membres publiques  
  
|Name|Description|  
|----------|-----------------|  
|[BoolStruct::Member, données de membre](../windows/boolstruct-member-data-member.md)|Spécifie qu'un [ComPtr](../windows/comptr-class.md) gère, ou ne gère pas, la gestion de la durée de vie d'une interface.|  
  
## Hiérarchie d'héritage  
 `BoolStruct`  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType, opérateur](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)