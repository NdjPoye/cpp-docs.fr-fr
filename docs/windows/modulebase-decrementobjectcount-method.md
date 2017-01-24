---
title: "ModuleBase::DecrementObjectCount, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DecrementObjectCount (méthode)"
ms.assetid: a016fb07-a36e-40cd-bc7b-8f6e85e256e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleBase::DecrementObjectCount, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
virtual long DecrementObjectCount() = 0;  
```  
  
## Valeur de retour  
 Le nombre avant l'opération de décrémentation.  
  
## Notes  
 Si implémenté, décrémente le nombre d'objets suivis par le module.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ModuleBase, classe](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)