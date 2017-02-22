---
title: "source_link_manager, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::source_link_manager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_link_manager (classe)"
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# source_link_manager, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'objet `source_link_manager` gère les liens réseau entre les blocs de messagerie et les blocs `ISource`.  
  
## Syntaxe  
  
```  
template<  
   class _LinkRegistry  
>  
class source_link_manager;  
```  
  
#### Paramètres  
 `_LinkRegistry`  
 Registre de liens réseau.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`const_pointer`|Type qui fournit un pointeur vers un élément `const` dans un objet `source_link_manager`.|  
|`const_reference`|Type qui fournit une référence à un élément `const` stocké dans un objet `source_link_manager` pour la lecture et l'exécution d'opérations const.|  
|`iterator`|Type qui fournit un itérateur capable de lire ou modifier tout élément dans l'objet `source_link_manager`.|  
|`type`|Type de registre de liens qui est géré par l'objet `source_link_manager`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[source\_link\_manager::source\_link\_manager, constructeur](../Topic/source_link_manager::source_link_manager%20Constructor.md)|Construit un objet `source_link_manager`.|  
|[source\_link\_manager::~source\_link\_manager, destructeur](../Topic/source_link_manager::~source_link_manager%20Destructor.md)|Détruit l'objet `source_link_manager`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[source\_link\_manager::add, méthode](../Topic/source_link_manager::add%20Method.md)|Ajoute un lien source à l'objet `source_link_manager`.|  
|[source\_link\_manager::begin, méthode](../Topic/source_link_manager::begin%20Method.md)|Retourne un itérateur au premier élément dans l'objet `source_link_manager`.|  
|[source\_link\_manager::contains, méthode](../Topic/source_link_manager::contains%20Method.md)|Recherche un bloc spécifié dans le `network_link_registry` de cet objet `source_link_manager`.|  
|[source\_link\_manager::count, méthode](../Topic/source_link_manager::count%20Method.md)|Compte le nombre de blocs liés dans l'objet `source_link_manager`.|  
|[source\_link\_manager::reference, méthode](../Topic/source_link_manager::reference%20Method.md)|Acquiert une référence sur l'objet `source_link_manager`.|  
|[source\_link\_manager::register\_target\_block, méthode](../Topic/source_link_manager::register_target_block%20Method.md)|Inscrit le bloc cible qui contient cet objet `source_link_manager`.|  
|[source\_link\_manager::release, méthode](../Topic/source_link_manager::release%20Method.md)|Libère la référence sur l'objet `source_link_manager`.|  
|[source\_link\_manager::remove, méthode](../Topic/source_link_manager::remove%20Method.md)|Supprime un lien de l'objet `source_link_manager`.|  
|[source\_link\_manager::set\_bound, méthode](../Topic/source_link_manager::set_bound%20Method.md)|Définit le nombre maximal de liens source qui peuvent être ajoutés à cet objet `source_link_manager`.|  
  
## Notes  
 Actuellement, les références des blocs sources sont comptabilisées.  C'est un wrapper sur un objet `network_link_registry` qui autorise l'accès simultané aux liens et fournit la capacité de référencer les liens via des rappels.  Les blocs de messages \(`target_block`s ou `propagator_block`s\) doivent utiliser cette classe pour leurs liens source.  
  
## Hiérarchie d'héritage  
 `source_link_manager`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry, classe](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry, classe](../../../parallel/concrt/reference/multi-link-registry-class.md)