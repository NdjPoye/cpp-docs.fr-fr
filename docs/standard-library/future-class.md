---
title: "future, classe | Microsoft Docs"
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
  - "future/std::future"
dev_langs: 
  - "C++"
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# future, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un *objet de retour asynchrone*.  
  
## Syntaxe  
  
```  
template<class Ty>  
class future;  
```  
  
## Notes  
 Chaque *fournisseur asynchrone* standard retourne un objet dont le type est une instanciation de ce modèle.  Un objet `future` fournit le seul accès au fournisseur asynchrone auquel il est associé.  Si vous avez besoin de plusieurs objets de retour asynchrones associés au même fournisseur asynchrone, copiez l'objet `future` dans un objet [shared\_future](../standard-library/shared-future-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[future::future, constructeur](../Topic/future::future%20Constructor.md)|Construit un objet `future`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[future::get, méthode](../Topic/future::get%20Method.md)|Récupère le résultat stocké dans l'état asynchrone associé.|  
|[future::share, méthode](../Topic/future::share%20Method.md)|Convertit l'objet `shared_future` en chaîne.|  
|[future::valid, méthode](../Topic/future::valid%20Method.md)|Spécifie si l'objet n'est pas vide.|  
|[future::wait, méthode](../Topic/future::wait%20Method.md)|Bloque le thread actuel jusqu'à ce que l'état asynchrone associé soit prêt.|  
|[future::wait\_for, méthode](../Topic/future::wait_for%20Method.md)|Se bloque jusqu'à ce que l'état asynchrone associé soit prêt ou jusqu'à ce que la durée spécifiée soit écoulée.|  
|[future::wait\_until, méthode](../Topic/future::wait_until%20Method.md)|Se bloque jusqu'à ce que l'état asynchrone associé soit prêt ou jusqu'à un point spécifié dans le temps.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[future::operator\=, opérateur](../Topic/future::operator=%20Operator.md)|Transfère l'état asynchrone associé à partir d'un objet spécifié.|  
  
## Configuration requise  
 **En\-tête :** future  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)