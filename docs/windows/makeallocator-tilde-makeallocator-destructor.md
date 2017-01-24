---
title: "MakeAllocator::~MakeAllocator, destructeur | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~MakeAllocator, destructeur"
ms.assetid: f1299c5f-cc6b-4d4e-85d4-aee1be0e2b0a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator::~MakeAllocator, destructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
~MakeAllocator();  
```  
  
## Remarques  
 Libère l'instance actuelle de la classe MakeAllocator.  
  
 Ce destructeur supprime également la mémoire allouée sous\-jacente si nécessaire.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [MakeAllocator, classe](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)