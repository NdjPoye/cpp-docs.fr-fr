---
title: "call, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call (classe)"
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# call, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `call` est une source multiple, `target_block` classé qui appelle une fonction spécifiée lors de la réception d'un message.  
  
## Syntaxe  
  
```  
template<  
   class _Type,  
   class _FunctorType = std::tr1::function<void(_Type const&)>  
>  
class call : public target_block<multi_link_registry<ISource<_Type>>>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile des messages propagés à ce bloc.  
  
 `_FunctorType`  
 Signature des fonctions que ce bloc peut accepter.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[call::call, constructeur](../Topic/call::call%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `call`.|  
|[call::~call, destructeur](../Topic/call::~call%20Destructor.md)|Détruit le bloc de messagerie `call`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[call::process\_input\_messages, méthode](../Topic/call::process_input_messages%20Method.md)|Exécute la fonction d'appel sur les messages d'entrée.|  
|[call::process\_message, méthode](../Topic/call::process_message%20Method.md)|Traite un message accepté par ce bloc de messagerie `call`.|  
|[call::propagate\_message, méthode](../Topic/call::propagate_message%20Method.md)|Passe un message de façon asynchrone d'un bloc `ISource` à ce bloc de messagerie `call`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[call::send\_message, méthode](../Topic/call::send_message%20Method.md)|Passe de façon synchrone un message du bloc `ISource` au bloc de messagerie `call`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
|[call::supports\_anonymous\_source, méthode](../Topic/call::supports_anonymous_source%20Method.md)|Remplace la méthode `supports_anonymous_source` pour indiquer que le bloc peut recevoir des messages proposés par une source qui n'est pas liée. \(Remplace [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [target\_block](../../../parallel/concrt/reference/target-block-class.md)  
  
 `call`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Classe transformer](../../../parallel/concrt/reference/transformer-class.md)