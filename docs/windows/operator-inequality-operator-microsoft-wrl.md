---
title: "operator!=, op&#233;rateur (Microsoft::WRL) | Microsoft Docs"
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
  - "client/Microsoft::WRL::operator!="
dev_langs: 
  - "C++"
ms.assetid: 785435da-87a6-4454-9bce-9d288a96dc26
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator!=, op&#233;rateur (Microsoft::WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur d'inégalité pour les objets [ComPtr](../windows/comptr-class.md) et [ComPtrRef](../windows/comptrref-class.md).  
  
## Syntaxe  
  
```  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
WRL_NOTHROW bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### Paramètres  
 `a`  
 L'objet de gauche.  
  
 `b`  
 L'objet de droite.  
  
## Valeur de retour  
 `true` si les objets ne sont pas égaux ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)