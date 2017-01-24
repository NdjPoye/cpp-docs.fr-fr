---
title: "GetModuleBase, fonction | Microsoft Docs"
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
  - "implements/Microsoft::WRL::GetModuleBase"
dev_langs: 
  - "C++"
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetModuleBase, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Extrait un pointeur de [ModuleBase](../windows/modulebase-class.md) qui permet d'incrémenter et de décrémenter le décompte de références d'un objet [RuntimeClass](../windows/runtimeclass-class.md) .  
  
## Syntaxe  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## Valeur de retour  
 Un pointeur vers un objet `ModuleBase`.  
  
## Notes  
 Cette fonction est utilisée en interne pour incrémenter ou décrémenter des nombres de référence d'objet.  
  
 Vous pouvez utiliser cette fonction pour vérifier des nombres de références en appelant [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) et [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)