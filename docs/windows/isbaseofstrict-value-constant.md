---
title: "IsBaseOfStrict::value, constante | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict::value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value (constante)"
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsBaseOfStrict::value, constante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## Remarques  
 Inidique si un type est la base d'un autre.  
  
 `value` est `true` si le type `Base` est une classe de base du type `Derived`, sinon c'est `false`.  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [IsBaseOfStrict, structure](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)