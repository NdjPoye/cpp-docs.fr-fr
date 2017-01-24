---
title: "DeferrableEventArgs, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle utilisée pour les types d'arguments des événements différés.  
  
## Syntaxe  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### Paramètres  
 `TEventArgsInterface`  
 Type d'interface qui déclare les arguments d'un événement différé.  
  
 `TEventArgsClass`  
 Classe qui implémente `TEventArgsInterface`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[DeferrableEventArgs::GetDeferral \(méthode\)](../windows/deferrableeventargs-getdeferral-method.md)|Obtient une référence à l'objet [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) qui représente un événement différé.|  
|[DeferrableEventArgs::InvokeAllFinished \(méthode\)](../windows/deferrableeventargs-invokeallfinished-method.md)|Appelé pour indiquer que le traitement d'un événement différé est terminé.|  
  
## Notes  
 Les instances de cette classe sont passées aux gestionnaires des événements différés.  Les paramètres du modèle représentent une interface qui définit les détails des arguments d'événement pour un type spécifique d'événement différé, et une classe qui implémente cette interface.  
  
 La classe est présentée comme premier argument au gestionnaire d'événements qui traite l'événement différé.  Vous pouvez appeler la méthode [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) pour obtenir l'objet [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) qui fournit toutes les informations sur l'événement différé.  Une fois la gestion des événements terminée, vous devez appeler Complete sur l'objet Deferral.  Appelez ensuite [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) à la fin de la méthode de gestionnaire d'événements, ce qui garantit que l'achèvement de tous les événements différés est communiqué correctement.  
  
## Configuration requise  
 **En\-tête** : event.h  
  
 **Espace de noms** : Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)