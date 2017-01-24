---
title: "SimpleClassFactory::CreateInstance, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleClassFactory::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance (méthode)"
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleClassFactory::CreateInstance, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une instance de l'interface spécifiée.  
  
## Syntaxe  
  
```  
  
STDMETHOD(  
   CreateInstance  
)  
   (_Inout_opt_ IUnknown* pUnkOuter,   
   REFIID riid,   
   _Deref_out_ void** ppvObject);  
```  
  
#### Paramètres  
 `pUnkOuter`  
 Doit être `nullptr`; sinon, la valeur de retour est CLASS\_E\_NOAGGREGATION.  
  
 SimpleClassFactory ne prend pas en charge le regroupement.  Si le regroupement était pris en charge et l'objet créé faisait partie d'un agrégat, `pUnkOuter` serait un pointeur vers l'interface de contrôle d'IUnknown de l'agrégat.  
  
 `riid`  
 ID d'interface de l'objet à créer.  
  
 `ppvObject`  
 Lorsque cette opération se termine, le pointeur vers une instance de l'objet spécifié par le paramètre de modèle de la classe `riid`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Si le \_\_WRL\_STRICT est défini, une erreur d'assertion est émise si la classe de base spécifiée dans le paramètre de modèle de classe n'est pas dérivé de [RuntimeClass](../windows/runtimeclass-class.md), ou n'est pas configuré avec la valeur WinRt ou WinRtClassicComMix de l'énumération [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [SimpleClassFactory, classe](../windows/simpleclassfactory-class.md)