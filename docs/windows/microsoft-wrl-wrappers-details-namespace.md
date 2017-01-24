---
title: "Microsoft::WRL::Wrappers::Details, espace de noms | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details"
  - "internal/Microsoft::WRL::Details"
  - "async/Microsoft::WRL::Details"
  - "corewrappers/Microsoft::WRL::Wrappers::Details"
  - "client/Microsoft::WRL::Details"
  - "module/Microsoft::WRL::Details"
  - "event/Microsoft::WRL::Details"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Details (espace de noms)"
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL::Wrappers::Details, espace de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
namespace Microsoft::WRL::Wrappers::Details;  
```  
  
## Membres  
  
### Classes  
  
|Name|Description|  
|----------|-----------------|  
|[SyncLockT, classe](../windows/synclockt-class.md)|Représente un type pouvant prendre la propriété exclusive ou partagée d'une ressource.|  
|[SyncLockWithStatusT, classe](../windows/synclockwithstatust-class.md)|Représente un type pouvant prendre la propriété exclusive ou partagée d'une ressource.|  
  
### Méthodes  
  
|Name|Description|  
|----------|-----------------|  
|[CompareStringOrdinal, méthode](../windows/comparestringordinal-method.md)|Compare deux objets `HSTRING` spécifiés et retourne un entier qui indique leur position relative dans un ordre de tri.|  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)