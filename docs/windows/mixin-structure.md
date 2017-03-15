---
title: "MixIn, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::MixIn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MixIn (structure)"
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# MixIn, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Garantit qu'une classe d'exécution dérive des interfaces [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], le cas échéant, puis des interfaces COM classiques.  
  
## Syntaxe  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### Paramètres  
 `Derived`  
 Un type dérivé de la structure [Implements](../windows/implements-structure.md).  
  
 `MixInType`  
 Un type de base.  
  
 `hasImplements`  
 `true` si `MixInType` est dérivé de l'implémentation actuelle du type de base; sinon, `false`.  
  
## Remarques  
 Si une classe est à la fois dérivée de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et des interfaces de classe COM, la liste de la déclaration des classes doit d'abord répertorier toute interface [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] puis toute interface COM classique.  MixIn garantit que les interfaces sont spécifiées dans le bon ordre.  
  
## Hiérarchie d'héritage  
 `MixIn`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)