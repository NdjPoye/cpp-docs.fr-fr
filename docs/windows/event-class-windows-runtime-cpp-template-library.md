---
title: "Event, classe (biblioth&#232;que de mod&#232;les Windows Runtime C++) | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event"
dev_langs: 
  - "C++"
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event, classe (biblioth&#232;que de mod&#232;les Windows Runtime C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un événement.  
  
## Syntaxe  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Event::Event, constructeur \(bibliothèque de modèles Windows Runtime C\+\+\)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Initialise une nouvelle instance de la classe Event.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Event::operator\=, opérateur](../windows/event-operator-assign-operator.md)|Assigne la référence Event spécifiée à l'instance Event actuelle.|  
  
## Hiérarchie d'héritage  
 `HandleT`  
  
 `Event`  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)