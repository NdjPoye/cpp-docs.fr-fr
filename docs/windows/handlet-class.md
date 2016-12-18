---
title: "HandleT, classe | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT (classe)"
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un handle à un objet .  
  
## Syntaxe  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### Paramètres  
 `HandleTraits`  
 Une instance de la structure [HandleTraits](../windows/handletraits-structure.md) définissant les caractéristiques communes d'un handle.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`Traits`|Un synonyme de `HandleTraits`.|  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[HandleT::HandleT, constructeur](../windows/handlet-handlet-constructor.md)|Initialise une nouvelle instance de la classe HandleT.|  
|[HandleT::~HandleT, destructeur](../windows/handlet-tilde-handlet-destructor.md)|Libère une instance de la classe HandleT.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[HandleT::Attach, méthode](../windows/handlet-attach-method.md)|Associe le handle spécifié avec l'objet HandleT actuel.|  
|[HandleT::Close, méthode](../windows/handlet-close-method.md)|Ferme l'objet HandleT en cours.|  
|[HandleT::Detach, méthode](../windows/handlet-detach-method.md)|Dissocie l'objet HandleT actuel de son handle sous\-jacent.|  
|[HandleT::Get, méthode](../windows/handlet-get-method.md)|Obtient la valeur du handle sous\-jacent.|  
|[HandleT::IsValid, méthode](../windows/handlet-isvalid-method.md)|Indique si l'objet HandleT actuel représente un handle.|  
  
### Méthodes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[HandleT::InternalClose, méthode](../windows/handlet-internalclose-method.md)|Ferme l'objet HandleT en cours.|  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[HandleT::operator\=, opérateur](../windows/handlet-operator-assign-operator.md)|Déplace la valeur de l'objet HandleT spécifié vers l'objet HandleT actuel.|  
  
### Données membres protégées  
  
|Name|Description|  
|----------|-----------------|  
|[HandleT::handle\_, données de membre](../windows/handlet-handle-data-member.md)|Contient le handle représenté par l'objet HandleT.|  
  
## Hiérarchie d'héritage  
 `HandleT`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)