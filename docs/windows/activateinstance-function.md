---
title: "ActivateInstance, fonction | Microsoft Docs"
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
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance (fonction)"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivateInstance, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enregistre et récupère une instance d'un type spécifié défini dans un ID de classe spécifié.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### Paramètres  
 `T`  
 Un type à activer.  
  
 `activatableClassId`  
 Le nom de l'ID de classe définissant le paramètre `T`.  
  
 `instance`  
 Lorsque cette opération se termine, une référence à une instance de `T`.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, une erreur HRESULT indiquant la cause de l'erreur.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Windows::Foundation  
  
## Voir aussi  
 [Windows::Foundation, espace de noms](../windows/windows-foundation-namespace.md)