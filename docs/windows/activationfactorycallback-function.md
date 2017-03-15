---
title: "ActivationFactoryCallback, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::ActivationFactoryCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactoryCallback (fonction)"
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ActivationFactoryCallback, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### Paramètres  
 `activationId`  
 Handle vers une chaîne spécifiant un nom de classe d'exécution.  
  
 `ppFactory`  
 Lorsque cette opération se termine, une fabrique d'activation correspondant au paramètre `activationId`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi ; sinon, un HRESULT décrivant l'anomalie.  Les valeurs HRESULT d'échec possibles sont CLASS\_E\_CLASSNOTAVAILABLE et E\_INVALIDARG.  
  
## Remarques  
 Obtient la fabrique d'activation pour l'ID d'activation spécifié.  
  
 Le runtime Windows appelle cette fonction de rappel pour demander un objet spécifié par son nom de classe d'exécution.  
  
## Configuration requise  
 **En\-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)