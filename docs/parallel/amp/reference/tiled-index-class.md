---
title: "tiled_index, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tiled_index (classe)"
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# tiled_index, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit un index dans un objet [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md).  Cette classe possède des propriétés pour accéder aux éléments par rapport à l'origine locale de la mosaïque et par rapport à l'origine globale.  Pour plus d'informations sur les espaces en mosaïque, consultez [Utilisation des mosaïques](../../../parallel/amp/using-tiles.md).  
  
## Syntaxe  
  
```  
template <  
   int _Dim0,  
   int _Dim1 = 0,  
   int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
  
template <  
   int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### Paramètres  
 `_Dim0`  
 Longueur de la dimension la plus significative.  
  
 `_Dim1`  
 Longueur de la deuxième dimension la plus significative.  
  
 `_Dim2`  
 Longueur de la dimension la moins significative.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_index::tiled\_index, constructeur](../Topic/tiled_index::tiled_index%20Constructor.md)|Initialise une nouvelle instance de la classe `tile_index`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_index::get\_tile\_extent, méthode](../Topic/tiled_index::get_tile_extent%20Method.md)|Retourne un objet [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) qui présente les valeurs des arguments template [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) `_Dim0`, `_Dim1` et `_Dim2`.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_index::barrier, constante](../Topic/tiled_index::barrier%20Constant.md)|Stocke un objet [tile\_barrier](../../../parallel/amp/reference/tile-barrier-class.md) qui représente un cloisonnement de la mosaïque actuelle des threads.|  
|||  
|[tiled\_index::global, constante](../Topic/tiled_index::global%20Constant.md)|Stocke un objet [index](../../../parallel/amp/reference/index-class.md) de rang 1, 2 ou 3, qui représente l'index global d'un objet [grid](http://msdn.microsoft.com/fr-fr/f7d1b6a6-586c-4345-b09a-bfc26c492cb0).|  
|[tiled\_index::local, constante](../Topic/tiled_index::local%20Constant.md)|Stocke un objet `index` de rang 1, 2 ou 3, qui représente l'index relatif de la mosaïque actuelle d'un objet [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md).|  
|[tiled\_index::rank, constante](../Topic/tiled_index::rank%20Constant.md)|Stocke le rang de l'objet [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md).|  
|[tiled\_index::tile, constante](../Topic/tiled_index::tile%20Constant.md)|Stocke un objet `index` de rang 1, 2 ou 3 qui représente les coordonnées de la mosaïque actuelle d'un objet `tiled_extent`.|  
|[tiled\_index::tile\_dim0, constante](../Topic/tiled_index::tile_dim0%20Constant.md)|Stocke la longueur de la dimension la plus significative.|  
|[tiled\_index::tile\_dim1, constante](../Topic/tiled_index::tile_dim1%20Constant.md)|Stocke la longueur de la deuxième dimension la plus significative.|  
|[tiled\_index::tile\_dim2, constante](../Topic/tiled_index::tile_dim2%20Constant.md)|Stocke la longueur de la dimension la moins significative.|  
|[tiled\_index::tile\_origin, constante](../Topic/tiled_index::tile_origin%20Constant.md)|Stocke un objet `index` de rang 1, 2 ou 3 qui représente les coordonnées globales d'origine de la mosaïque actuelle dans un objet `tiled_extent`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_index::tile\_extent, données membres](../Topic/tiled_index::tile_extent%20Data%20Member.md)|Obtient un objet [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) qui présente les valeurs des arguments template [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md), des arguments template [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md) `_Dim0`, `_Dim1` et `_Dim2`.|  
  
## Hiérarchie d'héritage  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)