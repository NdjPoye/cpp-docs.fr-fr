---
title: "EventSource, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventSource (classe)"
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# EventSource, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un événement.  Les fonctions membres d'EventSource ajoutent, suppriment, et appellent des gestionnaires d'événements.  
  
## Syntaxe  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### Paramètres  
 `TDelegateInterface`  
 L'interface d'un délégué représentant un gestionnaire d'événements.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[EventSource::EventSource, constructeur](../windows/eventsource-eventsource-constructor.md)|Initialise une nouvelle instance de la classe EventSource.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[EventSource::Add, méthode](../windows/eventsource-add-method.md)|Ajoute le gestionnaire d'événements représenté par l'interface de délégué spécifiée à l'ensemble de gestionnaires de d'événements pour l'objet EventSource actuel.|  
|[EventSource::GetSize, méthode](../windows/eventsource-getsize-method.md)|Récupère le nombre de gestionnaires d'événements associés à l'objet EventSource actuel.|  
|[EventSource::InvokeAll, méthode](../windows/eventsource-invokeall-method.md)|Appelle chaque gestionnaire d'événements associé à l'objet EventSource actuel à l'aide des arguments et types d'arguments spécifiés.|  
|[EventSource::Remove, méthode](../windows/eventsource-remove-method.md)|Supprime le gestionnaire d'événements représenté par le jeton d'enregistrement d'événements spécifié de l'ensemble des gestionnaires de jeu d'événements associés à l'objet EventSource actuel.|  
  
### Données membres protégées  
  
|Name|Description|  
|----------|-----------------|  
|[EventSource::addRemoveLock\_, données de membre](../windows/eventsource-addremovelock-data-member.md)|Synchronise l'accès au tableau de [targets\_](../windows/eventsource-targets-data-member.md) lors d'ajout, de suppression, ou d'appel de gestionnaires d'événements.|  
|[EventSource::targets\_, données de membre](../windows/eventsource-targets-data-member.md)|Un tableau d'un ou plusieurs gestionnaires d'événements.|  
|[EventSource::targetsPointerLock\_, données de membre](../windows/eventsource-targetspointerlock-data-member.md)|Synchronise l'accès aux données membres internes même si les gestionnaires d'événements pour cet EventSource sont ajoutés, déplacés, ou appelés.|  
  
## Hiérarchie d'héritage  
 `EventSource`  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)