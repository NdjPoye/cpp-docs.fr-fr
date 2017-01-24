---
title: "HString::GetAddressOf, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf"
dev_langs: 
  - "C++"
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::GetAddressOf, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère un pointeur vers le handle du HSTRING sous\-jacent.  
  
## Syntaxe  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## Valeur de retour  
 Un pointeur vers le handle du HSTRING sous\-jacent.  
  
## Remarques  
 Après cette opération, la valeur de la chaîne du handle du HSTRING sous\-jacent est détruite.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)