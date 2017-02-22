---
title: "index, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "index (structure)"
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# index, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Définit un point d'index dimensionnel *N*.  
  
## Syntaxe  
  
```  
template <  
   int _Rank  
>  
class index;  
```  
  
#### Paramètres  
 `_Rank`  
 Rang ou nombre de dimensions.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[index::index, constructeur](../Topic/index::index%20Constructor.md)|Initialise une nouvelle instance de la classe `index`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[index::operator\-\-, opérateur](../Topic/index::operator--%20Operator.md)|Décrémente chaque élément de l'objet `index`.|  
|[index::operator\(mod\)\=, opérateur](../Topic/index::operator\(mod\)=%20Operator.md)|Calcule le modulo \(reste\) de chaque élément dans l'objet `index` lorsque cet élément est divisé par un nombre.|  
|[index::operator\*\=, opérateur](../Topic/index::operator*=%20Operator.md)|Multiplie chaque élément de l'objet `index` par un nombre.|  
|[index::operator\/\=, opérateur](../Topic/index::operator-=%20Operator2.md)|Divise chaque élément de l'objet `index` par un nombre.|  
|[index::operatorOperator](../Topic/index::operatorOperator.md)|Retourne l'élément à l'index spécifié.|  
|[index::operator\+\+, opérateur](../Topic/index::operator++%20Operator.md)|Incrémente chaque élément de l'objet `index`.|  
|[index::operator\+\=, opérateur](../Topic/index::operator+=%20Operator.md)|Ajoute le nombre spécifié à chaque élément de l'objet `index`.|  
|[index::operator\=, opérateur](../Topic/index::operator=%20Operator.md)|Copie le contenu de l'objet `index` spécifié dans cet objet.|  
|[index::operator\-\=, opérateur](../Topic/index::operator-=%20Operator1.md)|Soustrait le nombre spécifié de chaque élément de l'objet `index`.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[index::rank, constante](../Topic/index::rank%20Constant.md)|Stocke le rang de l'objet `index`.|  
  
## Hiérarchie d'héritage  
 `index`  
  
## Remarques  
 La structure `index` représente un vecteur de coordonnées des entiers de *N* qui spécifie une seule position dans un espace dimensionnel *N*.  Les valeurs du vecteur sont classées de la plus significative à la moins significative.  Vous pouvez récupérer les valeurs des composants à l'aide de [index::operator\=, opérateur](../Topic/index::operator=%20Operator.md).  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)