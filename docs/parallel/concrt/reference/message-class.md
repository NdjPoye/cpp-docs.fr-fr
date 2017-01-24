---
title: "message, classe | Microsoft Docs"
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
  - "agents/concurrency::message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message (classe)"
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# message, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Enveloppe de message de base qui contient la charge utile de données qui est passée entre des blocs de messagerie.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class message : public ::Concurrency::details::_Runtime_object;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de données de la charge utile dans le message.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`type`|Alias de type pour `_Type`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[message::message, constructeur](../Topic/message::message%20Constructor.md)|Surchargé.  Construit un objet `message`.|  
|[message::~message, destructeur](../Topic/message::~message%20Destructor.md)|Détruit l'objet `message`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[message::add\_ref, méthode](../Topic/message::add_ref%20Method.md)|Ajoute au décompte de références pour l'objet `message`.  Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.|  
|[message::msg\_id, méthode](../Topic/message::msg_id%20Method.md)|Retourne l'ID de l'objet `message`.|  
|[message::remove\_ref, méthode](../Topic/message::remove_ref%20Method.md)|Soustrait du nombre de références de l'objet `message`.  Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Données membres message::payload](../Topic/message::payload%20Data%20Member.md)|Charge utile de l'objet `message`.|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 `message`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)