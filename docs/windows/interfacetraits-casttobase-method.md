---
title: "InterfaceTraits::CastToBase, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToBase (méthode)"
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits::CastToBase, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
#### Paramètres  
 `T`  
 Le type de paramètre `ptr`.  
  
 `ptr`  
 Pointeur vers le type `T`.  
  
## Valeur de retour  
 Pointeur vers `Base`  
  
## Remarques  
 Caste le pointeur spécifié en un pointeur vers `Base`.  
  
 Pour plus d'informations sur `Base`, consultez la section Typedefs Publiques dans [InterfaceTraits, structure](../windows/interfacetraits-structure.md).  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [InterfaceTraits, structure](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)