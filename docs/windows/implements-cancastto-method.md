---
title: "Implements::CanCastTo, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Implements::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo (méthode)"
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implements::CanCastTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient un pointeur vers l'interface spécifiée.  
  
## Syntaxe  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Paramètres  
 `riid`  
 Une référence à un ID d'interface.  
  
 `ppv`  
 En cas de réussite, un pointeur vers l'interface spécifiée par `riid`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur, telle que E\_NOINTERFACE.  
  
## Remarques  
 C'est une fonction d'assistance interne qui effectue une opération de QueryInterface.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Implements, structure](../windows/implements-structure.md)