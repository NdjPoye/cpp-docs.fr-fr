---
title: "ComPtr::operator!=, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator!="
dev_langs: 
  - "C++"
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator!=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si deux objets ComPtr ne sont pas égaux.  
  
## Syntaxe  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### Paramètres  
 `a`  
 Une référence à un objet ComPtr.  
  
 `b`  
 Une référence à un autre objet ComPtr.  
  
## Valeur de retour  
 Le premier opérateur produit `true` si l'objet `a` n'est pas égal à un objet `b`; sinon, `false`.  
  
 Les deuxième et troisième opérateurs produisent `true` si l'objet `a` n'est pas égal à `nullptr`; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)   
 [ComPtr, classe](../windows/comptr-class.md)