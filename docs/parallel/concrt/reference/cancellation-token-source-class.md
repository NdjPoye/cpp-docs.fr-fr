---
title: "cancellation_token_source, classe | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_source (classe)"
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_source, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `cancellation_token_source` représente la capacité à annuler une opération annulable.  
  
## Syntaxe  
  
```  
class cancellation_token_source;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token\_source::cancellation\_token\_source, constructeur](../Topic/cancellation_token_source::cancellation_token_source%20Constructor.md)|Surchargé.  Construit une nouvelle `cancellation_token_source`.  La source peut être utilisée pour signaler l'annulation d'une opération annulable.|  
|[cancellation\_token\_source::~cancellation\_token\_source, destructeur](../Topic/cancellation_token_source::~cancellation_token_source%20Destructor.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token\_source::cancel, méthode](../Topic/cancellation_token_source::cancel%20Method.md)|Annule le jeton.  Un `task_group`, `structured_task_group`ou `task`, qui utilise le jeton sera annulé sur cet appel et lèvera une exception au point d'interruption suivant.|  
|[cancellation\_token\_source::create\_linked\_source, méthode](../Topic/cancellation_token_source::create_linked_source%20Method.md)|Surchargé.  Crée un `cancellation_token_source` qui est annulé lorsque le jeton fourni est annulé.|  
|[cancellation\_token\_source::get\_token, méthode](../Topic/cancellation_token_source::get_token%20Method.md)|Retourne un jeton d'annulation associé à cette source.  Le jeton retourné peut être interrogé pour l'annulation ou fournir un rappel si et quand l'annulation se produit.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token\_source::operator\!\=, opérateur](../Topic/cancellation_token_source::operator!=%20Operator.md)||  
|[cancellation\_token\_source::operator\=, opérateur](../Topic/cancellation_token_source::operator=%20Operator.md)||  
|[cancellation\_token\_source::operator\=\=, opérateur](../Topic/cancellation_token_source::operator==%20Operator.md)||  
  
## Hiérarchie d'héritage  
 `cancellation_token_source`  
  
## Configuration requise  
 **En\-tête:** pplcancellation\_token.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)