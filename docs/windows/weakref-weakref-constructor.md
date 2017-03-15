---
title: "WeakRef::WeakRef, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef, constructeur"
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# WeakRef::WeakRef, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe WeakRef.  
  
## Syntaxe  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### Paramètres  
 `ptr`  
 Un pointeur, une référence, ou une référence rvalue à un objet existant qui initialise l'objet WeakRef actuel.  
  
## Remarques  
 Le premier constructeur initialise un objet WeakRef vide.  Le deuxième constructeur initialise un objet WeakRef à partir d'un pointeur vers l'interface IWeakReference.  Le troisième constructeur initialise un objet WeakRef à partir d'une référence à un objet ComPtr\< IWeakReference\> .  Les quatrième et cinquième constructeurs initialisent un objet WeakRef à partir d'un autre objet WeakRef.  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [WeakRef, classe](../windows/weakref-class.md)