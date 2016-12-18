---
title: "network_link_registry, classe | Microsoft Docs"
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
  - "agents/concurrency::network_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "network_link_registry (classe)"
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# network_link_registry, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe de base abstraite `network_link_registry` gère les liens entre les blocs source et cibles.  
  
## Syntaxe  
  
```  
template<  
   class _Block  
>  
class network_link_registry;  
```  
  
#### Paramètres  
 `_Block`  
 Type de données de bloc qui est stocké dans l'objet `network_link_registry`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`const_pointer`|Type qui fournit un pointeur vers un élément `const` dans un objet `network_link_registry`.|  
|`const_reference`|Type qui fournit une référence à un élément `const` stocké dans un objet `network_link_registry` pour la lecture et l'exécution d'opérations const.|  
|`iterator`|Type qui fournit un itérateur capable de lire ou modifier tout élément dans un objet `network_link_registry`.|  
|`type`|Type qui représente le type de bloc stocké dans l'objet `network_link_registry`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[network\_link\_registry::add, méthode](../Topic/network_link_registry::add%20Method.md)|En cas de remplacement dans une classe dérivée, ajoute un lien à l'objet `network_link_registry`.|  
|[network\_link\_registry::begin, méthode](../Topic/network_link_registry::begin%20Method.md)|En cas de substitution dans une classe dérivée, retourne un itérateur au premier élément dans l'objet `network_link_registry`.|  
|[network\_link\_registry::contains, méthode](../Topic/network_link_registry::contains%20Method.md)|En cas de substitution dans une classe dérivée, recherche un bloc spécifié dans l'objet `network_link_registry`.|  
|[network\_link\_registry::count, méthode](../Topic/network_link_registry::count%20Method.md)|En cas de substitution dans une classe dérivée, retourne le nombre d'éléments dans l'objet `network_link_registry`.|  
|[network\_link\_registry::remove, méthode](../Topic/network_link_registry::remove%20Method.md)|En cas de substitution dans une classe dérivée, supprime un bloc spécifié de l'objet `network_link_registry`.|  
  
## Notes  
 `network link registry` n'est pas sécurisé pour l'accès simultané.  
  
## Hiérarchie d'héritage  
 `network_link_registry`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry, classe](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry, classe](../../../parallel/concrt/reference/multi-link-registry-class.md)