---
title: "ClassFactory::QueryInterface, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface (méthode)"
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::QueryInterface, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère un pointeur vers l'interface spécifiée par paramètre.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### Paramètres  
 `riid`  
 Un ID d'interface.  
  
 `ppvObject`  
 Lorsque cet opération se termine, un pointeur vers l'interface spécifiée par le paramètre `riid`.  
  
## Valeur de retour  
 S\_OK si réussie; sinon, un HRESULT décrivant l'anomalie.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ClassFactory, classe](../windows/classfactory-class.md)