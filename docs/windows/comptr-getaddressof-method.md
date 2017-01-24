---
title: "ComPtr::GetAddressOf, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf (méthode)"
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::GetAddressOf, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère l'adresse du membre de données [ptr\_](../windows/comptr-ptr-data-member.md), contenant un pointeur vers l'interface représentée par ce ComPtr.  
  
## Syntaxe  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## Valeur de retour  
 L'adresse d'une variable.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)