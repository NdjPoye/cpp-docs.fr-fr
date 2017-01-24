---
title: "HandleT::HandleT, constructeur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT, constructeur"
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::HandleT, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe HandleT.  
  
## Syntaxe  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Paramètres  
 `h`  
 Handle.  
  
## Remarques  
 Le premier constructeur initialise un objet HandleT qui n'est pas un handle valide à un objet.  Le deuxième constructeur crée un objet HandleT à partir du paramètre `h`.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)