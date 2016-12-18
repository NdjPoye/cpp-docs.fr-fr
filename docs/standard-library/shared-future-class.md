---
title: "shared_future, classe | Microsoft Docs"
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
  - "future/std::shared_future"
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shared_future, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un *objet de retour asynchrone*.  Contrairement à un objet [futur](../standard-library/future-class.md), un *fournisseur asynchrone* peut être associé à plusieurs objets `shared_future`  
  
## Syntaxe  
  
```  
template<class Ty>  
class shared_future;  
```  
  
## Notes  
 N'appelez pas de méthode autre que `valid`, `operator=`, et le destructeur sur un objet `shared_future` qui est *vide*.  
  
 les objets `shared_future` ne sont pas synchronisés.  Les méthodes d'appel sur le même objet par des threads multiples présente une course de données qui a des résultats imprévisibles.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[shared\_future::shared\_future, constructeur](../Topic/shared_future::shared_future%20Constructor.md)|Construit un objet `shared_future`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[shared\_future::get, méthode](../Topic/shared_future::get%20Method.md)|Récupère le résultat stocké dans *l'état asynchrone associé*.|  
|[shared\_future::valid, méthode](../Topic/shared_future::valid%20Method.md)|Spécifie si l'objet n'est pas vide.|  
|[shared\_future::wait, méthode](../Topic/shared_future::wait%20Method.md)|Bloque le thread actuel jusqu'à ce que l'état asynchrone associé soit prêt.|  
|[shared\_future::wait\_for, méthode](../Topic/shared_future::wait_for%20Method.md)|Se bloque jusqu'à ce que l'état asynchrone associé soit prêt ou jusqu'à ce que la durée spécifiée soit écoulée.|  
|[shared\_future::wait\_until, méthode](../Topic/shared_future::wait_until%20Method.md)|Se bloque jusqu'à ce que l'état asynchrone associé soit prêt ou jusqu'à un point spécifié dans le temps.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[shared\_future::operator\=, opérateur](../Topic/shared_future::operator=%20Operator.md)|Affecte un nouvel état asynchrone associé.|  
  
## Configuration requise  
 **En\-tête :** future  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)