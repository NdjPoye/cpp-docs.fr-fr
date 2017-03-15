---
title: "ComPtr::Swap, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::Swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Swap (méthode)"
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ComPtr::Swap, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Echange l'interface managée par le ComPtr actuel avec l'interface managée par le ComPtr spécifié.  
  
## Syntaxe  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### Paramètres  
 `r`  
 Un ComPtr.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)