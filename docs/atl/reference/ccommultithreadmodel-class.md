---
title: "CComMultiThreadModel Class | Microsoft Docs"
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
  - "CComMultiThreadModel"
  - "ATL.CComMultiThreadModel"
  - "ATL::CComMultiThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, multithreading"
  - "CComMultiThreadModel class"
  - "threads (ATL)"
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComMultiThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModel` fournit des méthodes thread\-safe pour incrémenter ou décrémenter la valeur d'une variable.  
  
## Syntaxe  
  
```  
  
class CComMultiThreadModel  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)|Classe [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)de références.|  
|[CComMultiThreadModel::CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)|Classe [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)de références.|  
|[CComMultiThreadModel::ThreadModelNoCS](../Topic/CComMultiThreadModel::ThreadModelNoCS.md)|Classe [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)de références.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComMultiThreadModel::Decrement](../Topic/CComMultiThreadModel::Decrement.md)|\(Statique\) décrémente la valeur de la variable spécifiée en mode thread\-safe.|  
|[CComMultiThreadModel::Increment](../Topic/CComMultiThreadModel::Increment.md)|\(Statique\) incrémente la valeur de la variable spécifiée en mode thread\-safe.|  
  
## Notes  
 En général, vous utilisez `CComMultiThreadModel` via un des deux noms d' `typedef` , [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) ou [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  La classe référencée par chaque `typedef` dépend du modèle de thread utilisé, comme indiqué dans le tableau suivant :  
  
|typedef|Monothread|Thread cloisonné \(STA\)|Modèle de thread libre|  
|-------------|----------------|------------------------------|----------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComMultiThreadModel` lui\-même définit trois noms d' `typedef` .  `AutoCriticalSection` et `CriticalSection` référencent des classes qui fournissent des méthodes pour obtenir et libérer la propriété d'une section critique.  Classe [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)de références d'`ThreadModelNoCS` .  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CComSingleThreadModel Class](../../atl/reference/ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)