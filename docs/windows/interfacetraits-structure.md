---
title: "InterfaceTraits, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceTraits (structure)"
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### Paramètres  
 `I0`  
 Le nom d'une interface.  
  
 `CloakedType`  
 Pour RuntimeClass, Impléments et ChainInterfaces, une interface qui ne sera pas dans la liste des IDs d'interface pris en charge.  
  
## Remarques  
 Implémente les fonctionnalités communes d'une interface.  
  
 Le second modèle est une spécialisation pour les interfaces masquées.  Le troisième modèle est une spécialisation pour les paramètres Nil.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Base`|Un synonyme pour le paramètre de modèle `I0`.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo, méthode](../windows/interfacetraits-cancastto-method.md)|Indique si le pointeur spécifié peut être casté en un pointeur vers `Base`.|  
|[InterfaceTraits::CastToBase, méthode](../windows/interfacetraits-casttobase-method.md)|Caste le pointeur spécifié en un pointeur vers `Base`.|  
|[InterfaceTraits::CastToUnknown, méthode](../windows/interfacetraits-casttounknown-method.md)|Caste le pointeur spécifié en un pointeur vers IUnknown.|  
|[InterfaceTraits::FillArrayWithIid, méthode](../windows/interfacetraits-fillarraywithiid-method.md)|Assigne l'ID d'interface de `Base` à l'élément de tableau spécifié par l'argument d'index.|  
|[InterfaceTraits::Verify, méthode](../windows/interfacetraits-verify-method.md)|Vérifie que Base est correctement dérivée.|  
  
### Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[InterfaceTraits::IidCount, constante](../windows/interfacetraits-iidcount-constant.md)|Contient le nombre d'IDs d'interface associés à l'objet InterfaceTraits actuel.|  
  
## Hiérarchie d'héritage  
 `InterfaceTraits`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)