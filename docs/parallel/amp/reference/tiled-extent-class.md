---
title: "tiled_extent, classe | Microsoft Docs"
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
  - "amp/Concurrency::tiled_extent"
dev_langs: 
  - "C++"
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# tiled_extent, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un objet `tiled_extent` est un objet `extent` d'une à trois dimensions qui subdivise l'espace d'extent en mosaïques de une, deux, ou trois dimensions.  
  
## Syntaxe  
  
```  
template <  
   int _Dim0,  
   int _Dim1,  
   int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
  
template <  
   int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
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
|[tiled\_extent::tiled\_extent, constructeur](../Topic/tiled_extent::tiled_extent%20Constructor.md)|Initialise une nouvelle instance de la classe `tiled_extent`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_extent::get\_tile\_extent, méthode](../Topic/tiled_extent::get_tile_extent%20Method.md)|Retourne un objet `extent` qui capture les valeurs des arguments template `tiled_extent` `_Dim0`, `_Dim1` et `_Dim2`.|  
|[tiled\_extent::pad, méthode](../Topic/tiled_extent::pad%20Method.md)|Retourne un nouvel objet `tiled_extent` avec les étendues définies pour être également divisibles par les dimensions de la mosaïque.|  
|[tiled\_extent::truncate, méthode](../Topic/tiled_extent::truncate%20Method.md)|Retourne un nouvel objet `tiled_extent` avec les étendues sous\-ajustées pour être également divisibles par les dimensions de la mosaïque.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_extent::operator\=, opérateur](../Topic/tiled_extent::operator=%20Operator.md)|Copie le contenu de l'objet `tiled_index` spécifié dans cet objet.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_extent::tile\_dim0, constante](../Topic/tiled_extent::tile_dim0%20Constant.md)|Stocke la longueur de la dimension la plus significative.|  
|[tiled\_extent::tile\_dim1, constante](../Topic/tiled_extent::tile_dim1%20Constant.md)|Stocke la longueur de la deuxième dimension la plus significative.|  
|[tiled\_extent::tile\_dim2, constante](../Topic/tiled_extent::tile_dim2%20Constant.md)|Stocke la longueur de la dimension la moins significative.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[tiled\_extent::tile\_extent, données membres](../Topic/tiled_extent::tile_extent%20Data%20Member.md)|Obtient un objet `extent` qui capture les valeurs des arguments template `tiled_extent` `_Dim0`, `_Dim1` et `_Dim2`.|  
  
## Hiérarchie d'héritage  
 `extent`  
  
 `tiled_extent`  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)