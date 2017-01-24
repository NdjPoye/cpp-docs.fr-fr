---
title: "packaged_task, classe | Microsoft Docs"
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
  - "future/std::packaged_task"
dev_langs: 
  - "C++"
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# packaged_task, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un *fournisseur asynchrone* qui est un wrapper d'appel et dont la signature d'appel est `Ty(ArgTypes...)`.  Son *état asynchrone associé* contient une copie de l'objet appelé en plus du résultat potentiel.  
  
## Syntaxe  
  
```  
template<class>  
class packaged_task;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[packaged\_task::packaged\_task, constructeur](../Topic/packaged_task::packaged_task%20Constructor.md)|Construit un objet `packaged_task`.|  
|[packaged\_task::~packaged\_task, destructeur](../Topic/packaged_task::~packaged_task%20Destructor.md)|Détruit un objet `packaged_task`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[packaged\_task::get\_future, méthode](../Topic/packaged_task::get_future%20Method.md)|Retourne un objet [futur](../standard-library/future-class.md) ayant le même état asynchrone associé.|  
|[packaged\_task::make\_ready\_at\_thread\_exit, méthode](../Topic/packaged_task::make_ready_at_thread_exit%20Method.md)|Appelle l'objet appelable stocké dans l'état asynchrone associé et enregistre atomiquement la valeur retournée.|  
|[packaged\_task::reset, méthode](../Topic/packaged_task::reset%20Method.md)|Remplace l'état asynchrone associé.|  
|[packaged\_task::swap, méthode](../Topic/packaged_task::swap%20Method.md)|Échange l'état asynchrone avec celui d'un objet spécifié.|  
|[packaged\_task::valid, méthode](../Topic/packaged_task::valid%20Method.md)|Indique si l'objet a un état asynchrone associé.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[packaged\_task::operator\=, opérateur](../Topic/packaged_task::operator=%20Operator.md)|Transfère un état asynchrone associé à partir depuis un objet spécifié.|  
|[packaged\_task::operator\(\), opérateur](../Topic/packaged_task::operator\(\)%20Operator.md)|Appelle l'objet appelable stocké dans l'état asynchrone associé, stocke automatiquement la valeur renvoyée, et définit l'état sur *prêt*.|  
|[packaged\_task::operator bool, opérateur](../Topic/packaged_task::operator%20bool%20Operator.md)|Indique si l'objet a un état asynchrone associé.|  
  
## Configuration requise  
 **En\-tête :** future  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)