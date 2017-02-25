---
title: "multi_link_registry, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::multi_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multi_link_registry (classe)"
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# multi_link_registry, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'objet `multi_link_registry` est un `network_link_registry` qui gère plusieurs blocs source ou plusieurs blocs cibles.  
  
## Syntaxe  
  
```  
template<  
   class _Block  
>  
class multi_link_registry : public network_link_registry<_Block>;  
```  
  
#### Paramètres  
 `_Block`  
 Type de données de bloc qui est stocké dans l'objet `multi_link_registry`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[multi\_link\_registry::multi\_link\_registry, constructeur](../Topic/multi_link_registry::multi_link_registry%20Constructor.md)|Construit un objet `multi_link_registry`.|  
|[multi\_link\_registry::~multi\_link\_registry, destructeur](../Topic/multi_link_registry::~multi_link_registry%20Destructor.md)|Détruit l'objet `multi_link_registry`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[multi\_link\_registry::add, méthode](../Topic/multi_link_registry::add%20Method.md)|Ajoute un lien à l'objet `multi_link_registry`. \(Substitue [network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md).\)|  
|[multi\_link\_registry::begin, méthode](../Topic/multi_link_registry::begin%20Method.md)|Retourne un itérateur au premier élément dans l'objet `multi_link_registry`. \(Substitue [network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md).\)|  
|[multi\_link\_registry::contains, méthode](../Topic/multi_link_registry::contains%20Method.md)|Recherche un bloc spécifié dans l'objet `multi_link_registry`. \(Substitue [network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md).\)|  
|[multi\_link\_registry::count, méthode](../Topic/multi_link_registry::count%20Method.md)|Compte le nombre d'éléments dans l'objet `multi_link_registry`. \(Substitue [network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md).\)|  
|[multi\_link\_registry::remove, méthode](../Topic/multi_link_registry::remove%20Method.md)|Supprime un lien de l'objet `multi_link_registry`. \(Substitue [network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md).\)|  
|[multi\_link\_registry::set\_bound, méthode](../Topic/multi_link_registry::set_bound%20Method.md)|Définit une limite supérieure du nombre de liens que l'objet `multi_link_registry` peut contenir.|  
  
## Hiérarchie d'héritage  
 [network\_link\_registry](../../../parallel/concrt/reference/network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry, classe](../../../parallel/concrt/reference/single-link-registry-class.md)