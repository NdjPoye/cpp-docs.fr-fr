---
title: "texture_view, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# texture_view, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit un accès en lecture et en écriture à une texture.  `texture_view` ne peut être utilisé que pour lire des textures dont le type de valeur est `int`, `unsigned int` ou `float` qui a le bpse 32 bits par défaut.  Pour en savoir plus sur d'autres formats de texture, utilisez `texture_view<const _Value_type, _Rank>`.  
  
## Syntaxe  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view : public details::_Texture_base<_Value_type, _Rank>;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view<const _Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
```  
  
#### Paramètres  
 `_Value_type`  
 Type des éléments dans l'agrégat de texture.  
  
 `_Rank`  
 Rang de l'objet `texture_view`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`value_type`|Type des éléments dans les agrégats de texture.|  
|`coordinates_type`|Le type de la coordonnée utilisée pour spécifier un texel dans `texture_view`, autrement dit, un `short_vector` ayant le même rang que la texture associée qui a un type valeur de `float`.|  
|`gather_return_type`|Le type de retour utilisé pour rassembler des opérations, c'est\-à\-dire un rang 4 `short_vector` qui détient les quatre composantes de couleur homogènes rassemblés à partir des quatre valeurs de texel échantillonnées.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[texture\_view::texture\_view, constructeur](../Topic/texture_view::texture_view%20Constructor.md)|Surchargé.  Construit une instance `texture_view`.|  
|[texture\_view::~texture\_view, destructeur](../Topic/texture_view::~texture_view%20Destructor.md)|Détruit l'instance `texture_view`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[texture\_view::gather\_alpha, méthode](../Topic/texture_view::gather_alpha%20Method.md)|Surchargé.  Échantillonne la texture aux coordonnées spécifiées en utilisant la configuration d'échantillonnage spécifiée et retourne les composants alpha \(w\) des quatre texels échantillonnés.|  
|[texture\_view::gather\_blue, méthode](../Topic/texture_view::gather_blue%20Method.md)|Surchargé.  Échantillonne la texture aux coordonnées spécifiées en utilisant la configuration d'échantillonnage spécifiée et retourne les composants bleus \(z\) des quatre texels échantillonnés.|  
|[texture\_view::gather\_green, méthode](../Topic/texture_view::gather_green%20Method.md)|Surchargé.  Échantillonne la texture aux coordonnées spécifiées en utilisant la configuration d'échantillonnage spécifiée et retourne les composants verts \(y\) des quatre texels échantillonnés.|  
|[texture\_view::gather\_red, méthode](../Topic/texture_view::gather_red%20Method.md)|Surchargé.  Échantillonne la texture aux coordonnées spécifiées en utilisant la configuration d'échantillonnage spécifiée et retourne les composants rouges \(x\) des quatre texels échantillonnés.|  
|[texture\_view::get, méthode](../Topic/texture_view::get%20Method.md)|Surchargé.  Obtient la valeur de l'élément en fonction de son index.|  
|[texture\_view::sample, méthode](../Topic/texture_view::sample%20Method.md)|Surchargé.  Échantillonne la texture aux coordonnées et au niveau de détail spécifiés en utilisant la configuration d'échantillonnage spécifiée.|  
|[texture\_view::set, méthode](../Topic/texture_view::set%20Method.md)|Définit la valeur d'annotation d'un élément par index.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[texture\_view::operator\(\), opérateur](../Topic/texture_view::operator\(\)%20Operator.md)|Surchargé.  Obtient la valeur de l'élément en fonction de son index.|  
|[texture\_view::operatorOperator](../Topic/texture_view::operatorOperator.md)|Surchargé.  Obtient la valeur de l'élément en fonction de son index.|  
|[texture\_view::operator\=, opérateur](../Topic/texture_view::operator=%20Operator.md)|Surchargé.  Opérateur d'assignation|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[texture\_view::value\_type, membre de données](../Topic/texture_view::value_type%20Data%20Member.md)|Type de valeur des éléments de `texture_view`.|  
  
## Hiérarchie d'héritage  
 `_Texture_base`  
  
 `texture_view`  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms :** concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)