---
title: "Event::Event, constructeur (biblioth&#232;que de mod&#232;les Windows Runtime C++) | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::Event"
dev_langs: 
  - "C++"
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event::Event, constructeur (biblioth&#232;que de mod&#232;les Windows Runtime C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe Event.  
  
## Syntaxe  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### Paramètres  
 `h`  
 Handle vers un événement.  Par défaut, `h` est initialisé avec la valeur `nullptr`.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Event, classe \(bibliothèque de modèles Windows Runtime C\+\+\)](../windows/event-class-windows-runtime-cpp-template-library.md)