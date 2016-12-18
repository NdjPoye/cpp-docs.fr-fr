---
title: "CComSingleThreadModel Class | Microsoft Docs"
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
  - "ATL.CComSingleThreadModel"
  - "CComSingleThreadModel"
  - "ATL::CComSingleThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSingleThreadModel class"
  - "single-threaded applications"
  - "single-threaded applications, ATL"
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSingleThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour incrémenter ou décrémenter la valeur d'une variable.  
  
## Syntaxe  
  
```  
  
class CComSingleThreadModel  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](../Topic/CComSingleThreadModel::AutoCriticalSection.md)|Classe [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)de références.|  
|[CComSingleThreadModel::CriticalSection](../Topic/CComSingleThreadModel::CriticalSection.md)|Classe `CComFakeCriticalSection`de références.|  
|[CComSingleThreadModel::ThreadModelNoCS](../Topic/CComSingleThreadModel::ThreadModelNoCS.md)|Référence `CComSingleThreadModel`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComSingleThreadModel::Decrement](../Topic/CComSingleThreadModel::Decrement.md)|Décrémente la valeur de la variable spécifiée.  Cette implémentation n'est pas thread\-safe.|  
|[CComSingleThreadModel::Increment](../Topic/CComSingleThreadModel::Increment.md)|Incrémente la valeur de la variable spécifiée.  Cette implémentation n'est pas thread\-safe.|  
  
## Notes  
 `CComSingleThreadModel` fournit des méthodes pour incrémenter ou décrémenter la valeur d'une variable.  Contrairement à [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et de [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), ces méthodes ne sont pas thread\-safe.  
  
 En général, vous utilisez `CComSingleThreadModel` via un des deux noms d' `typedef` , [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) ou [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  La classe référencée par chaque `typedef` dépend du modèle de thread utilisé, comme indiqué dans le tableau suivant :  
  
|typedef|Modèle monothread|Modèle de thread cloisonné|Modèle de thread libre|  
|-------------|-----------------------|--------------------------------|----------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComSingleThreadModel` lui\-même définit trois noms d' `typedef` .  Références `CComSingleThreadModel`d'`ThreadModelNoCS` .  `AutoCriticalSection` et `CriticalSection` font référence à la classe [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), qui fournit des méthodes vides associées à obtention et libérer la propriété d'une section critique.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)