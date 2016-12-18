---
title: "HandleT::operator=, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur)"
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déplace la valeur de l'objet HandleT spécifié vers l'objet HandleT actuel.  
  
## Syntaxe  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Paramètres  
 `h`  
 Une référence rvalue à un handle.  
  
## Valeur de retour  
 Une référence à l'objet HandleT actuel.  
  
## Remarques  
 Cette opération invalide l'objet HandleT spécifié par le paramètre `h`.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)