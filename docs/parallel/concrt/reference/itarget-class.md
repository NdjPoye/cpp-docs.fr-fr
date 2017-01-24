---
title: "ITarget, classe | Microsoft Docs"
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
  - "agents/concurrency::ITarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITarget (classe)"
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ITarget, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `ITarget` est l'interface pour tous les blocs cibles.  Les blocs cible consomment des messages offerts à eux par les blocs `ISource`.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class ITarget;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de données de la charge utile dans les messages acceptés par le bloc cible.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`filter_method`|Signature de toute méthode utilisée par le bloc qui retourne une valeur `bool` pour déterminer si un message proposé doit être accepté.|  
|`type`|Alias de type pour `_Type`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ITarget::~ITarget, destructeur](../Topic/ITarget::~ITarget%20Destructor.md)|Détruit l'objet `ITarget`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ITarget::propagate, méthode](../Topic/ITarget::propagate%20Method.md)|En cas de substitution dans une classe dérivée, passe de façon asynchrone un message d'un bloc source à ce bloc cible.|  
|[ITarget::send, méthode](../Topic/ITarget::send%20Method.md)|En cas de substitution dans une classe dérivée, passe un message au bloc cible de façon synchrone.|  
|[ITarget::supports\_anonymous\_source, méthode](../Topic/ITarget::supports_anonymous_source%20Method.md)|Une fois substitués dans une classe dérivée, renvoie true ou false selon que le bloc de message reçoit des messages proposés par une source qui n'y est pas liée.  Si la méthode substituée retourne `true`, la cible ne peut pas remettre un message proposé, car la consommation d'un message remis ultérieurement requiert à la source d'être identifiée dans le registre de lien de sourse.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[ITarget::link\_source, méthode](../Topic/ITarget::link_source%20Method.md)|En cas de substitution dans une classe dérivée, lie un bloc source spécifié à ce bloc `ITarget`.|  
|[ITarget::unlink\_source, méthode](../Topic/ITarget::unlink_source%20Method.md)|En cas de substitution dans une classe dérivée, dissocie un bloc source spécifié de ce bloc `ITarget`.|  
|[ITarget::unlink\_sources, méthode](../Topic/ITarget::unlink_sources%20Method.md)|En cas de substitution dans une classe dérivée, dissocie tous les blocs source de ce bloc `ITarget`.|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 `ITarget`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource, classe](../../../parallel/concrt/reference/isource-class.md)