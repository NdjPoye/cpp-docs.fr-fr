---
title: "combinable, classe | Microsoft Docs"
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
  - "ppl/concurrency::combinable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable (classe)"
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# combinable, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'objet `combinable<T>` vise à fournir des copies des données spécifiques au thread pour exécuter des sous\-calculs locaux de thread sans verrou pendant des algorithmes parallèles.  À la fin de l'opération en parallèle, les sous\-calculs spécifiques au thread peuvent être fusionnés en un résultat final.  Cette classe peut être utilisée à la place d'une variable partagée et peut améliorer les performances si la variable partagée est susceptible de provoquer de nombreux conflits.  
  
## Syntaxe  
  
```  
template<  
   typename _Ty  
>  
class combinable;  
```  
  
#### Paramètres  
 `_Ty`  
 Type de données du résultat fusionné final.  Le type doit avoir un constructeur de copie et un constructeur par défaut.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[combinable::combinable, constructeur](../Topic/combinable::combinable%20Constructor.md)|Surchargé.  Construit un nouvel objet `combinable`.|  
|[combinable::~combinable, destructeur](../Topic/combinable::~combinable%20Destructor.md)|Détruit un objet `combinable`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[combinable::clear, méthode](../Topic/combinable::clear%20Method.md)|Efface tous résultats de calcul intermédiaires d'une utilisation précédente.|  
|[combinable::combine, méthode](../Topic/combinable::combine%20Method.md)|Calcule une valeur finale à partir du jeu de sous\-calculs de threads locaux en appelant la fonction d'association fournie.|  
|[combinable::combine\_each, méthode](../Topic/combinable::combine_each%20Method.md)|Calcule une valeur finale à partir du jeu de sous\-calculs de threads locaux en appelant la fonction d'association fournie une fois pour chaque sous\-calcul de thread local.  Le résultat final est accumulé par l'objet de fonction.|  
|[combinable::local, méthode](../Topic/combinable::local%20Method.md)|Surchargé.  Retourne une référence au sous\-calcul de thread privé.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[combinable::operator\=, opérateur](../Topic/combinable::operator=%20Operator.md)|Assigne à un objet `combinable` à partir d'un autre objet `combinable`.|  
  
## Notes  
 Pour plus d'informations, consultez [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Hiérarchie d'héritage  
 `combinable`  
  
## Configuration requise  
 **En\-tête :** ppl.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)