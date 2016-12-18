---
title: "MakeAllocator::Allocate, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator::Allocate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allocate (méthode)"
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator::Allocate, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
__forceinline void* Allocate();  
```  
  
## Valeur de retour  
 En cas de réussite, un pointeur vers la mémoire allouée; sinon, `nullptr`.  
  
## Remarques  
 Alloue de la mémoire et l'associe à l'objet MakeAllocator actuel.  
  
 La taille de la mémoire allouée est la taille du type spécifié par le paramètre de modèle MakeAllocator actuel.  
  
 Un développeur doit redéfinir uniquement la méthode Allocate\(\) pour implémenter un modèle d'allocation de mémoire différent.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [MakeAllocator, classe](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)