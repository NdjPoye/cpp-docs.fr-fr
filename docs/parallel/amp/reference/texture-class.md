---
title: "texture, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::texture"
dev_langs: 
  - "C++"
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# texture, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Une texture est un agrégat de données sur `accelerator_view` dans le domaine de l'extent.  Il s'agit d'une collection de variables, une pour chaque élément dans un domaine d'étendue.  Chaque variable contient une valeur correspondant au type primitif du C\+\+ \(`unsigned int`, `int`, `float`, `double`\), un type scalaire \(`norm` ou `unorm`\) ou un type vectoriel court.  
  
## Syntaxe  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture;  
```  
  
#### Paramètres  
 `_Value_type`  
 Type des éléments dans la texture.  
  
 `_Rank`  
 Rang de la texture.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`scalar_type`|Types scalaires.|  
|`value_type`|Types valeur.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[texture::texture, constructeur](../Topic/texture::texture%20Constructor.md)|Initialise une nouvelle instance de la classe [texture](../../../parallel/amp/reference/texture-class.md).|  
|[texture::~texture, destructeur](../Topic/texture::~texture%20Destructor.md)|Détruit l'objet [texture](../../../parallel/amp/reference/texture-class.md).|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[texture::copy\_to, méthode](../Topic/texture::copy_to%20Method.md)|Copie l'objet [texture](../../../parallel/amp/reference/texture-class.md) vers la destination, en faisant une copie complète.|  
|[texture::data, méthode](../Topic/texture::data%20Method.md)|Retourne un pointeur CPU vers les données brutes de cette texture.|  
|[texture::get, méthode](../Topic/texture::get%20Method.md)|Retourne la valeur de l'élément à l'index spécifié.|  
|[texture::get\_associated\_accelerator\_view, méthode](../Topic/texture::get_associated_accelerator_view%20Method.md)|Retourne l'[accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md) qui correspond à la cible par défaut dans laquelle copier cette texture.|  
|[texture::get\_depth\_pitch, méthode](../Topic/texture::get_depth_pitch%20Method.md)|Retourne le nombre d'octets entre chaque secteur de profondeur dans une texture 3D intermédiaire de l'UC.|  
|[texture::get\_row\_pitch, méthode](../Topic/texture::get_row_pitch%20Method.md)|Retourne le nombre d'octets entre chaque ligne dans une texture 2D ou 3D intermédiaire de l'UC.|  
|[texture::set, méthode](../Topic/texture::set%20Method.md)|Définit la valeur de l'élément à l'index spécifié.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[texture::operator\(\), opérateur](../Topic/texture::operator\(\)%20Operator.md)|Retourne la valeur de l'élément qui est spécifiée par les paramètres.|  
|[texture::operatorOperator](../Topic/texture::operatorOperator.md)|Retourne l'élément à l'index spécifié.|  
|[texture::operator\=, opérateur](../Topic/texture::operator=%20Operator.md)|Copie l'objet [texture](../../../parallel/amp/reference/texture-class.md) spécifié à celui\-ci.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[texture::rank, constante](../Topic/texture::rank%20Constant.md)|Obtient le rang de l'objet [texture](../../../parallel/amp/reference/texture-class.md).|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[texture::associated\_accelerator\_view, membre de données](../Topic/texture::associated_accelerator_view%20Data%20Member.md)|Obtient l'[accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md) qui correspond à la cible par défaut dans laquelle copier cette texture.|  
|[texture::depth\_pitch, membre de données](../Topic/texture::depth_pitch%20Data%20Member.md)|Obtient le nombre d'octets entre chaque secteur de profondeur dans une texture 3D intermédiaire de l'UC.|  
|[texture::row\_pitch, membre de données](../Topic/texture::row_pitch%20Data%20Member.md)|Obtient le nombre d'octets entre chaque ligne dans une texture 2D ou 3D intermédiaire de l'UC.|  
  
## Hiérarchie d'héritage  
 `_Texture_base`  
  
 `texture`  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)