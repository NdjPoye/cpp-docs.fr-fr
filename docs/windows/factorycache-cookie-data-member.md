---
title: "FactoryCache::cookie, donn&#233;es de membre | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache::cookie"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cookie (membre de données)"
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache::cookie, donn&#233;es de membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## Notes  
 Contient une valeur identifiant un [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] enregistré ou un objet de classe COM, et utilisée ultérieurement pour effacer l'objet.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [FactoryCache, structure](../windows/factorycache-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)