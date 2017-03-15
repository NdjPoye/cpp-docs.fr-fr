---
title: "InterfaceList, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceList (structure)"
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceList, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### Paramètres  
 `T`  
 Un nom d'interface; la première interface dans la liste récursive.  
  
 `U`  
 Un nom d'interface; les interfaces restantes dans la liste récursive.  
  
## Notes  
 Utilisé pour créer une liste récurrente d'interfaces.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`FirstT`|Synonyme du paramètre de modèle `T`.|  
|`RestT`|Synonyme du paramètre de modèle `U`.|  
  
## Hiérarchie d'héritage  
 `InterfaceList`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)