---
title: "ChainInterfaces, structure | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChainInterfaces (structure)"
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie les fonctions de vérification et d'initialisation pouvant être appliquées à un ensemble d'IDs d'interface.  
  
## Syntaxe  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### Paramètres  
 `I0`  
 \(Requis\) ID d'interface 0.  
  
 `I1`  
 \(Requis\) ID d'interface 1.  
  
 `I2`  
 \(Facultatif\) ID d'interface 2.  
  
 `I3`  
 \(Facultatif\) ID d'interface 3.  
  
 `I4`  
 \(Facultatif\) ID d'interface 4.  
  
 `I5`  
 \(Facultatif\) ID d'interface 5.  
  
 `I6`  
 \(Facultatif\) ID d'interface 6.  
  
 `I7`  
 \(Facultatif\) ID d'interface 7.  
  
 `I8`  
 \(Facultatif\) ID d'interface 8.  
  
 `I9`  
 \(Facultatif\) ID d'interface 9.  
  
 `DerivedType`  
 Un type dérivé.  
  
 `BaseType`  
 Le type de base d'un type dérivé.  
  
 `hasImplements`  
 Valeur booléenne qui à `true`, signifie que vous ne pouvez pas utiliser une structure [MixIn](../windows/mixin-structure.md) avec une classe ne dérivant pas de la structure [Impléments](../windows/implements-structure.md).  
  
## Membres  
  
### Méthodes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo, méthode](../windows/chaininterfaces-cancastto-method.md)|Indique si l'ID d'interface spécifié peut être casté à chacune des spécialisations définies par les paramètres de modèle ChainInterface.|  
|[ChainInterfaces::CastToUnknown, méthode](../windows/chaininterfaces-casttounknown-method.md)|Caste le pointeur d'interface de type défini par le paramètre de modèle `I0` vers un pointeur sur IUnknown.|  
|[ChainInterfaces::FillArrayWithIid, méthode](../windows/chaininterfaces-fillarraywithiid-method.md)|Stocke l'ID d'interface défini par le paramètre de modèle `I0` à un emplacement spécifié dans un tableau d'IDs d'interface spécifié.|  
|[ChainInterfaces::Verify, méthode](../windows/chaininterfaces-verify-method.md)|Vérifie que chaque interface définie par les paramètres de modèle `I0` dans `I9` hérite d'IUnknown et\/ou d'IInspectable, et que `I0` hérite de `I1` via `I9`.|  
  
### Constantes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[ChainInterfaces::IidCount, constante](../windows/chaininterfaces-iidcount-constant.md)|Le nombre total d'IDs d'interface contenus dans les interfaces spécifiées par des paramètres de modèle `I0` dans `I9`.|  
  
## Hiérarchie d'héritage  
 `I0`  
  
 `ChainInterfaces`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)