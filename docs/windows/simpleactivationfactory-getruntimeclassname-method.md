---
title: "SimpleActivationFactory::GetRuntimeClassName, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::GetRuntimeClassName, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le nom de la classe d'exécution d'une instance de la classe spécifiée par le paramètre de modèle de la classe de `Base`.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### Paramètres  
 `runtimeName`  
 Lorsque cette opération se termine, le nom de la classe d'exécution.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Si \_\_WRL\_STRICT est défini, une erreur d'assertion est émise si la classe spécifiée dans le paramètre de modèle de la classe `Base` n'est pas dérivé de [RuntimeClass](../windows/runtimeclass-class.md) , ou n'est pas configuré avec la valeur WinRt ou WinRtClassicComMix de l'énumération de [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [SimpleActivationFactory, classe](../windows/simpleactivationfactory-class.md)