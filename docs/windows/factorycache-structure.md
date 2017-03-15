---
title: "FactoryCache, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FactoryCache (structure)"
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
struct FactoryCache;  
```  
  
## Notes  
 Contient l'emplacement d'une fabrique de classe et une valeur qui identifie soit un objet wrt stocké, soit un objet de la classe COM.  
  
## Membres  
  
### Données membres publiques  
  
|Name|Description|  
|----------|-----------------|  
|[FactoryCache::cookie, données de membre](../windows/factorycache-cookie-data-member.md)|Contient une valeur identifiant un [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] enregistré ou un objet de classe COM, et utilisée ultérieurement pour effacer l'objet.|  
|[FactoryCache::factory, données de membre](../windows/factorycache-factory-data-member.md)|Pointe vers un [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou une fabrique de classe COM.|  
  
## Hiérarchie d'héritage  
 `FactoryCache`  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)