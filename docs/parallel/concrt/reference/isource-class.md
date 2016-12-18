---
title: "ISource, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ISource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISource (classe)"
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISource, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `ISource` est l'interface pour tous les blocs source.  Les blocs source propagent des messages aux blocs `ITarget`.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class ISource;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de données de la charge utile dans les messages produits par le bloc source.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`source_type`|Alias de type pour `_Type`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ISource::~ISource, destructeur](../Topic/ISource::~ISource%20Destructor.md)|Détruit l'objet `ISource`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ISource::accept, méthode](../Topic/ISource::accept%20Method.md)|En cas de substitution dans une classe dérivée, accepte un message qui a été offert par ce bloc `ISource`, en transférant la propriété à l'appelant.|  
|[ISource::acquire\_ref, méthode](../Topic/ISource::acquire_ref%20Method.md)|En cas de substitution dans une classe dérivée, acquiert un décompte de références sur ce bloc `ISource` pour empêcher la suppression.|  
|[ISource::consume, méthode](../Topic/ISource::consume%20Method.md)|En cas de substitution dans une classe dérivée, consomme un message précédemment offert par ce bloc `ISource`et réservé avec succès par la cible, en transférant la propriété à l'appelant.|  
|[ISource::link\_target, méthode](../Topic/ISource::link_target%20Method.md)|En cas de substitution dans une classe dérivée, lie un bloc cible à ce bloc `ISource`.|  
|[ISource::release, méthode](../Topic/ISource::release%20Method.md)|En cas de substitution dans une classe dérivée, émet une réservation de message réussie précédente.|  
|[ISource::release\_ref, méthode](../Topic/ISource::release_ref%20Method.md)|En cas de substitution dans une classe dérivée, émet un décompte de références sur ce bloc `ISource`.|  
|[ISource::reserve, méthode](../Topic/ISource::reserve%20Method.md)|En cas de substitution dans une classe dérivée, réserve un message précédemment offert par ce bloc `ISource`.|  
|[ISource::unlink\_target, méthode](../Topic/ISource::unlink_target%20Method.md)|En cas de substitution dans une classe dérivée, dissocie un bloc cible de ce bloc `ISource`, s'il était auparavant lié.|  
|[ISource::unlink\_targets, méthode](../Topic/ISource::unlink_targets%20Method.md)|En cas de substitution dans une classe dérivée, dissocie tous les blocs cibles de ce bloc `ISource`.|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 `ISource`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget, classe](../../../parallel/concrt/reference/itarget-class.md)