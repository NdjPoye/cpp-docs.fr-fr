---
title: "cancellation_token, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token (classe)"
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# cancellation_token, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `cancellation_token` représente la capacité à déterminer si une opération d'annulation a été demandée.  Un jeton donné peut être associé à un `task_group`, `structured_task_group`, ou à une `task` pour fournir l'annulation implicite.  Il peut également être interrogé pour l'annulation ou avoir un rappel enregistré en cas d'annulation du `cancellation_token_source` associé.  
  
## Syntaxe  
  
```  
class cancellation_token;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token::cancellation\_token, constructeur](../Topic/cancellation_token::cancellation_token%20Constructor.md)||  
|[cancellation\_token::~cancellation\_token, destructeur](../Topic/cancellation_token::~cancellation_token%20Destructor.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token::deregister\_callback, méthode](../Topic/cancellation_token::deregister_callback%20Method.md)|Supprime un rappel précédemment enregistré via la méthode `register` basé sur l'objet `cancellation_token_registration` retourné au moment de l'inscription.|  
|[cancellation\_token::is\_cancelable, méthode](../Topic/cancellation_token::is_cancelable%20Method.md)|Retourne une indication si ce jeton peut être annulé ou non.|  
|[cancellation\_token::is\_canceled, méthode](../Topic/cancellation_token::is_canceled%20Method.md)|Retourne `true` si le jeton a été annulé.|  
|[cancellation\_token::none, méthode](../Topic/cancellation_token::none%20Method.md)|Retourne un jeton d'annulation qui ne pourra jamais être soumis à une annulation.|  
|[cancellation\_token::register\_callback, méthode](../Topic/cancellation_token::register_callback%20Method.md)|Enregistre une fonction de rappel avec le jeton.  Si et lorsque le jeton est annulé, le rappel s'effectuera.  Notez que si le jeton est déjà annulé au point où cette méthode est appelée, l'appel sera effectué immédiatement et de manière synchrone.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token::operator\!\=, opérateur](../Topic/cancellation_token::operator!=%20Operator.md)||  
|[cancellation\_token::operator\=, opérateur](../Topic/cancellation_token::operator=%20Operator.md)||  
|[cancellation\_token::operator\=\=, opérateur](../Topic/cancellation_token::operator==%20Operator.md)||  
  
## Hiérarchie d'héritage  
 `cancellation_token`  
  
## Configuration requise  
 **En\-tête :** pplcancellation\_token.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)