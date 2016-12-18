---
title: "extent, classe (C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent (structure)"
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# extent, classe (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente un vecteur de *N* entiers qui spécifient les limites d'un espace à *N* dimensions dont l'origine est 0.  Les valeurs du vecteur sont classées de la plus significative à la moins significative.  
  
## Syntaxe  
  
```  
template <  
   int _Rank>  
class extent;  
```  
  
#### Paramètres  
 `_Rank`  
 Rang de l'objet `extent`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[extent::extent, constructeur](../Topic/extent::extent%20Constructor.md)|Initialise une nouvelle instance de la classe `extent`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[extent::contains, méthode](../Topic/extent::contains%20Method.md)|Vérifie que l'objet `extent` spécifié a le rang spécifié.|  
|[extent::size, méthode](../Topic/extent::size%20Method.md)|Retourne la taille totale linéaire de l'étendue \(en unités d'éléments\).|  
|[extent::tile, méthode](../Topic/extent::tile%20Method.md)|Génère un objet `tiled_extent` avec les étendues de mosaïque données par les dimensions spécifiées.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[extent::operator\-, opérateur](../Topic/extent::operator-%20Operator.md)|Retourne un nouvel objet `extent` qui est créé en soustrayant les éléments `index` des éléments `extent` correspondants.|  
|[extent::operator\-\-, opérateur](../Topic/extent::operator--%20Operator.md)|Décrémente chaque élément de l'objet `extent`.|  
|[extent::operator\(mod\)\=, opérateur](../Topic/extent::operator\(mod\)=%20Operator.md)|Calcule le modulo \(reste\) de chaque élément dans l'objet `extent` lorsque cet élément est divisé par un nombre.|  
|[extent::operator\*\=, opérateur](../Topic/extent::operator*=%20Operator.md)|Multiplie chaque élément de l'objet `extent` par un nombre.|  
|[extent::operator\/\=, opérateur](../Topic/extent::operator-=%20Operator1.md)|Divise chaque élément de l'objet `extent` par un nombre.|  
|[extent::operatorOperator](../Topic/extent::operatorOperator.md)|Retourne l'élément à l'index spécifié.|  
|[extent::operator\+, opérateur](../Topic/extent::operator+%20Operator.md)|Retourne un nouvel objet `extent` qui est créé en ajoutant les éléments `index` et `extent` correspondants.|  
|[extent::operator\+\+, opérateur](../Topic/extent::operator++%20Operator.md)|Incrémente chaque élément de l'objet `extent`.|  
|[extent::operator\+\=, opérateur](../Topic/extent::operator+=%20Operator.md)|Ajoute le nombre spécifié à chaque élément de l'objet `extent`.|  
|[extent::operator\=, opérateur](../Topic/extent::operator=%20Operator.md)|Copie le contenu d'un autre objet `extent` dans celui\-ci.|  
|[extent::operator\-\=, opérateur](../Topic/extent::operator-=%20Operator2.md)|Soustrait le nombre spécifié de chaque élément de l'objet `extent`.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[extent::rank, constante](../Topic/extent::rank%20Constant.md)|Obtient le rang de l'objet `extent`.|  
  
## Hiérarchie d'héritage  
 `extent`  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)