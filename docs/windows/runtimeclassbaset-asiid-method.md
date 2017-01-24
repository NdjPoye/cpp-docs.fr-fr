---
title: "RuntimeClassBaseT::AsIID, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID (méthode)"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT::AsIID, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### Paramètres  
 `T`  
 Un type implémentant l'ID d'interface spécifié par le paramètre `riid`.  
  
 `implements`  
 Une variable du type spécifié par le paramètre `T`de modèle.  
  
 `riid`  
 L'ID d'interface à récupérer.  
  
 `ppvObject`  
 Si cette opération est réussie, un pointeur\-vers\-un\-pointeur vers l'interface spécifiée par le paramètre `riid`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT décrivant l'erreur.  
  
## Notes  
 Récupère un pointeur vers l'ID d'interface spécifié.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [RuntimeClassBaseT, structure](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)