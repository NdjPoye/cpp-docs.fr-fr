---
title: "CloakedIid, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::CloakedIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CloakedIid (structure)"
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CloakedIid, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique aux modèles RuntimeClass, Implémentations et ChainInterfaces que l'interface spécifiée n'est pas accessible dans la liste des IID.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### Paramètres  
 `T`  
 L'interface cachée \(masquée\).  
  
## Remarques  
 L'exemple suivant illustre la manière dont CloakedIid est utilisé : `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## Hiérarchie d'héritage  
 `T`  
  
 `CloakedIid`  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)