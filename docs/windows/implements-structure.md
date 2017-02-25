---
title: "Implements, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Implements (structure)"
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implements, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémente QueryInterface et GetIid pour les interfaces spécifiées.  
  
## Syntaxe  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
#### Paramètres  
 `I0`  
 Le zérotième ID d'interface. \(Obligatoire\)  
  
 `I1`  
 Le premier ID d'interface. \(facultatif\)  
  
 `I2`  
 Le deuxième ID d'interface. \(facultatif\)  
  
 `I3`  
 Le troisième ID d'interface. \(facultatif\)  
  
 `I4`  
 Quatrième ID d'interface. \(facultatif\)  
  
 `I5`  
 Le cinquième ID d'interface. \(facultatif\)  
  
 `I6`  
 Le sixième ID d'interface. \(facultatif\)  
  
 `I7`  
 Le septième ID d'interface. \(facultatif\)  
  
 `I8`  
 Huitième ID d'interface. \(facultatif\)  
  
 `I9`  
 Le neuvième ID d'interface. \(facultatif\)  
  
 `flags`  
 Indicateurs de configuration pour la classe.  Un ou plusieurs énumérations de [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) spécifiées dans une structure de [RuntimeClassFlags](../windows/runtimeclassflags-structure.md).  
  
## Remarques  
 Dérive de la liste d'interfaces spécifiées et implémente les modèles d'assistance pour QueryInterface et GetIid.  
  
 Chaque `I0` via le paramètre d'interface `I9` doit dériver d'IUnknown, IInspectable, ou du modèle [ChainInterfaces](../windows/chaininterfaces-structure.md).  Le paramètre `flags` détermine si la prise en charge est généré pour IUnknown ou IInspectable.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`ClassFlags`|Un synonyme de `RuntimeClassFlags<WinRt>`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[Implements::CanCastTo, méthode](../windows/implements-cancastto-method.md)|Obtient un pointeur vers l'interface spécifiée.|  
|[Implements::CastToUnknown, méthode](../windows/implements-casttounknown-method.md)|Obtient un pointeur vers l'interface IUnknown sous\-jacente.|  
|[Implements::FillArrayWithIid, méthode](../windows/implements-fillarraywithiid-method.md)|Insère l'ID d'interface spécifié par le zérotième paramètre de modèle actuel dans l'élément de tableau spécifié.|  
  
### Constantes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[Implements::IidCount, constante](../windows/implements-iidcount-constant.md)|Contient le nombre d'IDs d'interface implémentés.|  
  
## Hiérarchie d'héritage  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)