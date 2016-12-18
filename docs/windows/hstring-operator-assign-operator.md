---
title: "HString::Operator=, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator="
dev_langs: 
  - "C++"
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déplace la valeur d'un autre objet HString vers l'objet HString actuel.  
  
## Syntaxe  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
#### Paramètres  
 `other`  
 Un objet HString existant.  
  
## Remarques  
 La valeur de l'objet `other` existant est copiée vers l'objet HString actuel, puis l'objet `other` est détruit.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)