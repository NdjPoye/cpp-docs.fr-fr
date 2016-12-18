---
title: "RuntimeClassFlags, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClassFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassFlags (structure)"
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassFlags, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contient le type pour une instance d'une [RuntimeClass](../windows/runtimeclass-class.md).  
  
## Syntaxe  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### Paramètres  
 `flags`  
 Valeur [RuntimeClassType, énumération](../windows/runtimeclasstype-enumeration.md).  
  
## Membres  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[RuntimeClassFlags::value, constante](../windows/runtimeclassflags-value-constant.md)|Contient une valeur de [RuntimeClassType, énumération](../windows/runtimeclasstype-enumeration.md).|  
  
## Hiérarchie d'héritage  
 `RuntimeClassFlags`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)