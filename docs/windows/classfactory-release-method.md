---
title: "ClassFactory::Release, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "release (méthode)"
ms.assetid: 49da2002-f9d6-4d7f-8a65-48c20b1bf99f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::Release, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrémente le décompte de références de l'objet ClassFactory actuel.  
  
## Syntaxe  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## Valeur de retour  
 S\_OK si réussie; sinon, un HRESULT décrivant l'anomalie.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ClassFactory, classe](../windows/classfactory-class.md)