---
title: "progress_reporter, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::progress_reporter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progress_reporter (classe)"
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# progress_reporter, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe de rapporteur de progression permet de signaler les notifications de progression d'un type spécifique.  Chaque objet progress\_reporter est lié à une action ou une opération asynchrone particulière.  
  
## Syntaxe  
  
```  
template<  
   typename _ProgressType  
>  
class progress_reporter;  
```  
  
#### Paramètres  
 `_ProgressType`  
 Type de charge utile de chaque notification de progression signalée via le rapporteur de progression.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[progress\_reporter::progress\_reporter, constructeur](../Topic/progress_reporter::progress_reporter%20Constructor.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[progress\_reporter::report, méthode](../Topic/progress_reporter::report%20Method.md)|Envoie un rapport d'avancement à l'action ou à l'opération asynchrone à laquelle ce rapporteur de progression est lié.|  
  
## Notes  
 Ce type est uniquement disponible pour les applications Windows Store.  
  
## Hiérarchie d'héritage  
 `progress_reporter`  
  
## Configuration requise  
 **En\-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [create\_async, fonction](../Topic/create_async%20Function.md)