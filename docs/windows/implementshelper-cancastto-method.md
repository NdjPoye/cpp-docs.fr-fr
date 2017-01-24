---
title: "ImplementsHelper::CanCastTo, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo (méthode)"
ms.assetid: 9ae6fa17-d0b1-4e31-9ae5-da6ae4026e32
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ImplementsHelper::CanCastTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
  
HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
HRESULT CanCastTo(  
   _In_ const IID &iid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Paramètres  
 `riid`  
 Référence à un ID d'interface.  
  
 `ppv`  
 Si cette opération est réussie, un pointeur vers l'interface spécifiée par `riid` ou `iid`.  
  
 `iid`  
 Référence à un ID d'interface.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Notes  
 Obtient un pointeur vers l'ID d'interface spécifié.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ImplementsHelper, structure](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)