---
title: "ArgTraits::args, constante | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::ArgTraits::args"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "args (constante)"
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraits::args, constante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
static const int args = -1; ;  
```  
  
## Notes  
 Conserve le nombre de paramètres de la méthode Invoke d'une interface de délégué.  
  
## Remarques  
 Lorsque `args` est égal à \-1, il ne peut y avoir aucune correspondance pour la signature de la méthode Invoke.  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ArgTraits, structure](../windows/argtraits-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)