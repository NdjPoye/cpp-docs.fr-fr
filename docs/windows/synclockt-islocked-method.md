---
title: "SyncLockT::IsLocked, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked (méthode)"
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SyncLockT::IsLocked, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
bool IsLocked() const;  
```  
  
## Valeur de retour  
 **true** si l'objet SyncLockT est verrouillé; sinon **false**.  
  
## Notes  
 Indique si l'objet SyncLockT actuel possède une ressource; autrement dit, si l'objet SyncLockT est *verrouillé*.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [SyncLockT, classe](../windows/synclockt-class.md)