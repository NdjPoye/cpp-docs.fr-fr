---
title: "writeonly_texture_view, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::writeonly_texture_view"
dev_langs: 
  - "C++"
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# writeonly_texture_view, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Permet d'accéder en écriture seule à une texture.  
  
## Syntaxe  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view<_Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
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
|`scalar_type`||  
|`value_type`|Type des éléments dans la texture.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[writeonly\_texture\_view::writeonly\_texture\_view, constructeur](../Topic/writeonly_texture_view::writeonly_texture_view%20Constructor.md)|Initialise une nouvelle instance de la classe [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md).|  
|[writeonly\_texture\_view::~writeonly\_texture\_view, destructeur](../Topic/writeonly_texture_view::~writeonly_texture_view%20Destructor.md)|Détruit l'objet [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md).|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[writeonly\_texture\_view::set, méthode](../Topic/writeonly_texture_view::set%20Method.md)|Définit la valeur de l'élément à l'index spécifié.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[writeonly\_texture\_view::operator\=, opérateur](../Topic/writeonly_texture_view::operator=%20Operator.md)|Copie l'objet spécifié [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md) dans celui\-ci.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[writeonly\_texture\_view::rank, constante](../Topic/writeonly_texture_view::rank%20Constant.md)|Obtient le rang de l'objet [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md).|  
  
## Hiérarchie d'héritage  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)