---
title: "CComMultiThreadModelNoCS Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComMultiThreadModelNoCS"
  - "CComMultiThreadModelNoCS"
  - "ATL.CComMultiThreadModelNoCS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, multithreading"
  - "CComMultiThreadModelNoCS class"
  - "threads (ATL)"
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CComMultiThreadModelNoCS Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModelNoCS` fournit des méthodes thread\-safe pour incrémenter ou décrémenter la valeur d'une variable, sans verrou de section critique ou déverrouiller la fonctionnalité.  
  
## Syntaxe  
  
```  
  
class CComMultiThreadModelNoCS  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](../Topic/CComMultiThreadModelNoCS::AutoCriticalSection.md)|Classe [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)de références.|  
|[CComMultiThreadModelNoCS::CriticalSection](../Topic/CComMultiThreadModelNoCS::CriticalSection.md)|Classe `CComFakeCriticalSection`de références.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](../Topic/CComMultiThreadModelNoCS::ThreadModelNoCS.md)|Classe `CComMultiThreadModelNoCS`de références.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](../Topic/CComMultiThreadModelNoCS::Decrement.md)|\(Statique\) décrémente la valeur de la variable spécifiée en mode thread\-safe.|  
|[CComMultiThreadModelNoCS::Increment](../Topic/CComMultiThreadModelNoCS::Increment.md)|\(Statique\) incrémente la valeur de la variable spécifiée en mode thread\-safe.|  
  
## Notes  
 `CComMultiThreadModelNoCS` est semblable à [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) car il fournit des méthodes thread\-safe pour incrémenter ou décrémenter une variable.  Toutefois, lorsque vous référencez une classe de section critique dans `CComMultiThreadModelNoCS`, les méthodes telles que `Lock` et l' `Unlock` ne provoquent aucun effet.  
  
 En général, vous utilisez `CComMultiThreadModelNoCS` via le nom d' `ThreadModelNoCS``typedef` .  Cet `typedef` est défini dans `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, et [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Les noms globaux [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) et [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) d' `typedef` ne font pas `CComMultiThreadModelNoCS`.  
  
 En plus de `ThreadModelNoCS`, `CComMultiThreadModelNoCS` définit `AutoCriticalSection` et `CriticalSection`.  Référence de ces la dernière deux noms d' `typedef`[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), qui fournit des méthodes vides associée à obtenir et libérer une section critique.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)