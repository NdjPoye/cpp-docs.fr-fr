---
title: "single_link_registry, classe | Microsoft Docs"
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
  - "agents/concurrency::single_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_link_registry (classe)"
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# single_link_registry, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'objet `single_link_registry` est un `network_link_registry` qui gère uniquement un seul bloc source ou cible.  
  
## Syntaxe  
  
```  
template<  
   class _Block  
>  
class single_link_registry : public network_link_registry<_Block>;  
```  
  
#### Paramètres  
 `_Block`  
 Type de données de bloc qui est stocké dans l'objet `single_link_registry`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[single\_link\_registry::single\_link\_registry, constructeur](../Topic/single_link_registry::single_link_registry%20Constructor.md)|Construit un objet `single_link_registry`.|  
|[single\_link\_registry::~single\_link\_registry, destructeur](../Topic/single_link_registry::~single_link_registry%20Destructor.md)|Détruit l'objet `single_link_registry`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[single\_link\_registry::add, méthode](../Topic/single_link_registry::add%20Method.md)|Ajoute un lien à l'objet `single_link_registry`. \(Substitue [network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md).\)|  
|[single\_link\_registry::begin, méthode](../Topic/single_link_registry::begin%20Method.md)|Retourne un itérateur au premier élément dans l'objet `single_link_registry`. \(Substitue [network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md).\)|  
|[single\_link\_registry::contains, méthode](../Topic/single_link_registry::contains%20Method.md)|Recherche un bloc spécifié dans l'objet `single_link_registry`. \(Substitue [network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md).\)|  
|[single\_link\_registry::count, méthode](../Topic/single_link_registry::count%20Method.md)|Compte le nombre d'éléments dans l'objet `single_link_registry`. \(Substitue [network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md).\)|  
|[single\_link\_registry::remove, méthode](../Topic/single_link_registry::remove%20Method.md)|Supprime un lien de l'objet `single_link_registry`. \(Substitue [network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md).\)|  
  
## Hiérarchie d'héritage  
 [network\_link\_registry](../../../parallel/concrt/reference/network-link-registry-class.md)  
  
 `single_link_registry`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [multi\_link\_registry, classe](../../../parallel/concrt/reference/multi-link-registry-class.md)