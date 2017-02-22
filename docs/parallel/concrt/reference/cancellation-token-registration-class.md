---
title: "cancellation_token_registration, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration (classe)"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# cancellation_token_registration, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `cancellation_token_registration` représente une notification de rappel de `cancellation_token`.  Lorsque la méthode `register` sur `cancellation_token` est utilisée pour recevoir une notification relative à la date d'annulation, un objet `cancellation_token_registration` est retourné comme handle au rappel afin que l'appelant puisse demander qu'un rappel spécifique ne soit plus effectué via l'utilisation de la méthode `deregister`.  
  
## Syntaxe  
  
```  
class cancellation_token_registration;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token\_registration::cancellation\_token\_registration, constructeur](../Topic/cancellation_token_registration::cancellation_token_registration%20Constructor.md)||  
|[cancellation\_token\_registration::~cancellation\_token\_registration, destructeur](../Topic/cancellation_token_registration::~cancellation_token_registration%20Destructor.md)||  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[cancellation\_token\_registration::operator\!\=, opérateur](../Topic/cancellation_token_registration::operator!=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=, opérateur](../Topic/cancellation_token_registration::operator=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=\=, opérateur](../Topic/cancellation_token_registration::operator==%20Operator.md)||  
  
## Hiérarchie d'héritage  
 `cancellation_token_registration`  
  
## Configuration requise  
 **En\-tête :** pplcancellation\_token.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)