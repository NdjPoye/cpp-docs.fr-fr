---
title: "ComPtr::AsWeak, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak (méthode)"
ms.assetid: 23e29dcd-39cb-423f-abe6-6df4428213bf
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ComPtr::AsWeak, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Extrait une référence faible à l'objet actuel.  
  
## Syntaxe  
  
```  
HRESULT AsWeak(  
   _Out_ WeakRef* pWeakRef  
);  
```  
  
#### Paramètres  
 `pWeakRef`  
 Lorsque cette opération se termine, un pointeur vers un objet de référence faible.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)