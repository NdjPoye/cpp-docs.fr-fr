---
title: "AsWeak, fonction | Microsoft Docs"
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
  - "client/Microsoft::WRL::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak (fonction)"
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsWeak, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère une référence faible à une instance spécifiée.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### Paramètres  
 `T`  
 Un pointeur vers le type du paramètre `p`.  
  
 `p`  
 Une instance d'un type.  
  
 `pWeak`  
 Lorsque cette opération se termine, un pointeur vers une référence faible au paramètre `p`.  
  
## Valeur de retour  
 S\_OK, si cette opération est réussie; sinon, une erreur HRESULT indiquant la cause de l'échec.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)