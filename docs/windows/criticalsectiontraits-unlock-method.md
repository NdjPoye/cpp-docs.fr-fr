---
title: "CriticalSectionTraits::Unlock, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock (méthode)"
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSectionTraits::Unlock, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécialise un modèle CriticalSection afin qu'il prenne en charge la libération de la propriété de l'objet de section critique spécifié.  
  
## Syntaxe  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### Paramètres  
 `cs`  
 Un pointeur vers un objet de section critique.  
  
## Remarques  
 Le modificateur *Type* est défini comme `typedef CRITICAL_SECTION* Type;`.  
  
 Pour plus d'informations, consultez « La fonction LeaveCriticalSection » dans la section « Fonctions de synchronisation » de la documentation de l'API Windows.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [CriticalSectionTraits, structure](../windows/criticalsectiontraits-structure.md)