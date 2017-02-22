---
title: "critical_section, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::critical_section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical_section (classe)"
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# critical_section, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Mutex non réentrant qui est explicitement informé du runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class critical_section;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`native_handle_type`|Référence à un objet `critical_section`.|  
  
### Classes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[critical\_section::scoped\_lock, classe](../Topic/critical_section::scoped_lock%20Class.md)|Wrapper RAII sécurisé du point de vue des exceptions pour un objet `critical_section`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[critical\_section::critical\_section, constructeur](../Topic/critical_section::critical_section%20Constructor.md)|Construit une nouvelle section critique.|  
|[critical\_section::~critical\_section, destructeur](../Topic/critical_section::~critical_section%20Destructor.md)|Détruit une section critique.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[critical\_section::lock, méthode](../Topic/critical_section::lock%20Method.md)|Acquiert cette section critique.|  
|[critical\_section::native\_handle, méthode](../Topic/critical_section::native_handle%20Method.md)|Retourne le handle natif spécifique à une plateforme, s'il en existe un.|  
|[critical\_section::try\_lock, méthode](../Topic/critical_section::try_lock%20Method.md)|Essaie d'acquérir le verrou sans bloquer.|  
|[critical\_section::try\_lock\_for, méthode](../Topic/critical_section::try_lock_for%20Method.md)|Essaie d'acquérir le verrou sans blocage pour un nombre spécifique de millisecondes.|  
|[critical\_section::unlock, méthode](../Topic/critical_section::unlock%20Method.md)|Déverrouille la section critique.|  
  
## Notes  
 Pour plus d'informations, consultez [Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Hiérarchie d'héritage  
 `critical_section`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [reader\_writer\_lock, classe](../../../parallel/concrt/reference/reader-writer-lock-class.md)