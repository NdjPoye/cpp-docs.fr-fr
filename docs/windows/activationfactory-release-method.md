---
title: "ActivationFactory::Release, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "release (méthode)"
ms.assetid: 5bc25ff0-ee3c-4a2d-a9b6-2d8f158033ad
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactory::Release, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrémente le décompte de références de l'objet ActivationFactory actuel.  
  
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
 [ActivationFactory, classe](../windows/activationfactory-class.md)