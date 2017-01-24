---
title: "reader_writer_lock, classe | Microsoft Docs"
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
  - "concrt/concurrency::reader_writer_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reader_writer_lock (classe)"
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# reader_writer_lock, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Verrou de lecteur\/writer, basé sur file d'attente, à préférence de writer, à rotation uniquement locale.  Le verrou accorde un accès premier entré, premier sorti aux writers et prive les lecteurs sous une charge continue de writers.  
  
## Syntaxe  
  
```  
class reader_writer_lock;  
```  
  
## Membres  
  
### Classes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[reader\_writer\_lock::scoped\_lock, classe](../Topic/reader_writer_lock::scoped_lock%20Class.md)|Wrapper RAII sécurisé du point de vue des exceptions qui peut être utilisé pour acquérir des objets lock `reader_writer_lock` en tant que writer.|  
|[reader\_writer\_lock::scoped\_lock\_read, classe](../Topic/reader_writer_lock::scoped_lock_read%20Class.md)|Wrapper RAII sécurisé du point de vue des exceptions qui peut être utilisé pour acquérir des objets lock `reader_writer_lock` en tant que lecteur.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[reader\_writer\_lock::reader\_writer\_lock, constructeur](../Topic/reader_writer_lock::reader_writer_lock%20Constructor.md)|Construit un nouvel objet `reader_writer_lock`.|  
|[reader\_writer\_lock::~reader\_writer\_lock, destructeur](../Topic/reader_writer_lock::~reader_writer_lock%20Destructor.md)|Détruit l'objet `reader_writer_lock`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[reader\_writer\_lock::lock, méthode](../Topic/reader_writer_lock::lock%20Method.md)|Acquiert le verrou de lecteur\/writer en tant que writer.|  
|[reader\_writer\_lock::lock\_read, méthode](../Topic/reader_writer_lock::lock_read%20Method.md)|Acquiert le verrou de lecteur\/writer en tant que lecteur.  S'il existe des writers, les lecteurs actifs doivent attendre jusqu'à ce qu'ils soient terminés.  Le lecteur enregistre simplement un intérêt dans le verrou et attend que writers le libèrent.|  
|[reader\_writer\_lock::try\_lock, méthode](../Topic/reader_writer_lock::try_lock%20Method.md)|Tente d'acquérir le verrou de lecteur\/write en tant que writer sans blocage.|  
|[reader\_writer\_lock::try\_lock\_read, méthode](../Topic/reader_writer_lock::try_lock_read%20Method.md)|Tente d'acquérir le verrou de lecteur\/writer en tant que lecteur sans blocage.|  
|[reader\_writer\_lock::unlock, méthode](../Topic/reader_writer_lock::unlock%20Method.md)|Déverrouille le verrou writer\-lecteur selon qui l'a verrouillé, le lecteur ou le writer.|  
  
## Notes  
 Pour plus d'informations, consultez [Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Hiérarchie d'héritage  
 `reader_writer_lock`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section, classe](../../../parallel/concrt/reference/critical-section-class.md)