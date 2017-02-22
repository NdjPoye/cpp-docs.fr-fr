---
title: "RuntimeClass::GetIids, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids (méthode)"
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetIids, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient un tableau pouvant contenir les IDs d'interface implémentés par l'objet RuntimeClass actuel.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### Paramètres  
 `iidCount`  
 Lorsque cette opération se termine, le nombre total d'éléments du tableau `iids`.  
  
 `iids`  
 Lorsque cette opération se termine, un pointeur vers un tableau d'IDs d'interface.  
  
## Valeur de retour  
 S\_OK en cas de réussite; sinon E\_OUTOFMEMORY.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)