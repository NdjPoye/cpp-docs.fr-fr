---
title: "operator&lt;, op&#233;rateur (Microsoft::WRL) | Microsoft Docs"
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
  - "client/Microsoft::WRL::operator<"
dev_langs: 
  - "C++"
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt;, op&#233;rateur (Microsoft::WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine si l'adresse d'un objet est inférieure à celle d'une autre.  
  
## Syntaxe  
  
```cpp  
template<class T, class U>  
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();  
template<class T, class U>  
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();  
```  
  
#### Paramètres  
 `a`  
 L'objet de gauche.  
  
 `b`  
 L'objet de droite.  
  
## Valeur de retour  
 `true` si l'adresse de `a` est inférieure à celle de `b`; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)