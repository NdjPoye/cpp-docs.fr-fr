---
title: "GetActivationFactory, fonction | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::GetActivationFactory"
  - "client/ABI::Windows::Foundation::GetActivationFactory"
  - "client/Windows::Foundation::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory (fonction)"
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetActivationFactory, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère une fabrique d'activation pour le type spécifié par le paramètre de modèle.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### Paramètres  
 `T`  
 Un paramètre de modèle spécifiant le type de la fabrique d'activation.  
  
 `activatableClassId`  
 Le nom de la classe que la fabrique d'activation peut produire.  
  
 `factory`  
 Lorsque cette opération se termine, une référence à la fabrique d'activation pour le type `T`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, une erreur HRESULT indiquant la cause de l'échec.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Windows::Foundation  
  
## Voir aussi  
 [Windows::Foundation, espace de noms](../windows/windows-foundation-namespace.md)