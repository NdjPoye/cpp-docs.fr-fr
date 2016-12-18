---
title: "ArgTraitsHelper, structure | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper (structure)"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraitsHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### Paramètres  
 `TDelegateInterface`  
 Une interface de délégué.  
  
## Notes  
 Aide à définir les caractéristiques communes des arguments de délégué.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`methodType`|Un synonyme de `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Un synonyme de `ArgTraits<methodType>`.|  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[ArgTraitsHelper::args, constante](../windows/argtraitshelper-args-constant.md)|Aide [ArgTraits::args](../windows/argtraits-args-constant.md) à compter le nombre de paramètres de la méthode Invoke d'une interface de délégué.|  
  
## Hiérarchie d'héritage  
 `ArgTraitsHelper`  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)