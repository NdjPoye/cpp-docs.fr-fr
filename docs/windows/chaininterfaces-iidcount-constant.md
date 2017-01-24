---
title: "ChainInterfaces::IidCount, constante | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::IidCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IidCount (constante)"
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::IidCount, constante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le nombre total d'IDs d'interface contenus dans les interfaces spécifiées par des paramètres de modèle `I0` dans `I9`.  
  
## Syntaxe  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## Valeur de retour  
 Le nombre total d'IDs d'interface.  
  
## Remarques  
 Les paramètres de modèle `I0` et `I1`sont requis, et les paramètres `I2` via `I9` sont facultatifs. Le nombre d'IID de chaque interface est généralement 1.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ChainInterfaces, structure](../windows/chaininterfaces-structure.md)