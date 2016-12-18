---
title: "SimpleActivationFactory::ActivateInstance, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance (méthode)"
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory::ActivateInstance, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une instance de l'interface spécifiée.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   ActivateInstance  
)(_Deref_out_ IInspectable **ppvObject);  
```  
  
#### Paramètres  
 `ppvObject`  
 Lorsque cette opération se termine, le pointeur vers une instance de l'objet spécifié par le paramètre de modèle de la classe `Base`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Si le \_\_WRL\_STRICT est défini, une erreur d'assertion est émise si la classe de base spécifiée dans le paramètre de modèle de classe n'est pas dérivé de [RuntimeClass](../windows/runtimeclass-class.md), ou n'est pas configuré avec la valeur WinRt ou WinRtClassicComMix de l'énumération de [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [SimpleActivationFactory, classe](../windows/simpleactivationfactory-class.md)