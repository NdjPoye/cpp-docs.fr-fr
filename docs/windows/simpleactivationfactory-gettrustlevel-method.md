---
title: "SimpleActivationFactory::GetTrustLevel, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::GetTrustLevel, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le niveau de confiance d'une instance de la classe spécifiée par le paramètre de modèle de la classe `Base`.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### Paramètres  
 `trustLvl`  
 Lorsque cette opération se termine, le niveau de confiance de l'objet de la classe actuelle.  
  
## Valeur de retour  
 Toujours S\_OK.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [SimpleActivationFactory, classe](../windows/simpleactivationfactory-class.md)