---
title: "ClassFactory::AddRef, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef (méthode)"
ms.assetid: 5b091785-dea4-42b6-a502-0db5fc7a5a2e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::AddRef, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incrémente le décompte de références de l'objet ClassFactory actuel.  
  
## Syntaxe  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## Valeur de retour  
 S\_OK si réussie; sinon, un HRESULT décrivant l'anomalie.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ClassFactory, classe](../windows/classfactory-class.md)