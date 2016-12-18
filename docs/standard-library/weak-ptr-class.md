---
title: "weak_ptr, classe | Microsoft Docs"
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
  - "std.tr1.weak_ptr"
  - "tr1.weak_ptr"
  - "weak_ptr"
  - "tr1::weak_ptr"
  - "std::tr1::weak_ptr"
  - "memory/std::tr1::weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weak_ptr (classe)"
  - "weak_ptr (classe) (TR1)"
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# weak_ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule un pointeur faiblement lié.  
  
## Syntaxe  
  
```  
template<class Ty> class weak_ptr {  
public:  
    typedef Ty element_type;  
  
    weak_ptr();  
    weak_ptr(const weak_ptr&);  
    template<class Other>  
        weak_ptr(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr(const shared_ptr<Other>&);  
  
    weak_ptr& operator=(const weak_ptr&);  
    template<class Other>  
        weak_ptr& operator=(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr& operator=(shared_ptr<Other>&);  
  
    void swap(weak_ptr&);  
    void reset();  
  
    long use_count() const;  
    bool expired() const;  
    shared_ptr<Ty> lock() const;  
    };  
```  
  
#### Paramètres  
 `Ty`  
 Type contrôlé par le pointeur faible.  
  
## Notes  
 La classe de modèle décrit un objet qui pointe vers une ressource gérée par un ou plusieurs objets [shared\_ptr, classe](../standard-library/shared-ptr-class.md).  Les objets `weak_ptr` qui pointent vers une ressource n'affectent pas le décompte de références de la ressource.  Ainsi, quand le dernier objet `shared_ptr` qui gère cette ressource est détruit, la ressource est libérée, même s'il existe des objets `weak_ptr` pointant vers cette ressource.  Ceci est essentiel pour éviter les cycles de structures de données.  
  
 Un objet `weak_ptr` pointe vers une ressource s'il a été construit à partir d'un objet `shared_ptr` qui détient cette ressource, s'il a été construit à partir d'un objet `weak_ptr` qui pointe vers cette ressource ou si cette ressource lui a été assignée à l'aide d'[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md).  Un objet `weak_ptr` ne fournit pas un accès direct à la ressource vers laquelle il pointe.  Le code qui a besoin d'utiliser la ressource le fait via un objet `shared_ptr` qui détient cette ressource, créé en appelant la fonction membre [weak\_ptr::lock](../Topic/weak_ptr::lock.md).  Un objet `weak_ptr` a expiré quand la ressource vers laquelle il pointe a été libérée car tous les objets `shared_ptr` détenant la ressource ont été détruits.  L'appel de `lock` sur un objet `weak_ptr` qui a expiré crée un objet shared\_ptr vide.  
  
 Un objet weak\_ptr vide ne pointe vers aucune ressource et n'a aucun bloc de contrôle.  Sa fonction membre `lock` retourne un objet shared\_ptr vide.  
  
 Un cycle se produit quand plusieurs ressources contrôlées par des objets `shared_ptr` contiennent des objets `shared_ptr` qui se font référence mutuellement.  Par exemple, une liste circulaire liée avec trois éléments a un nœud principal `N0` ; ce nœud contient un objet `shared_ptr` qui possède le nœud suivant, `N1` ; ce nœud contient un objet `shared_ptr` qui possède le nœud suivant, `N2` ; ce nœud, à son tour, contient un objet `shared_ptr` qui possède le nœud principal, `N0`, ce qui ferme le cycle.  Dans cette situation, aucun des décomptes de références n'est jamais égal à zéro et les nœuds du cycle ne sont pas libérés.  Pour éliminer le cycle, le dernier nœud `N2` doit contenir un objet `weak_ptr` pointant vers `N0` au lieu d'un objet `shared_ptr`.  Puisque l'objet `weak_ptr` ne possède pas `N0`, il n'affecte pas le décompte de références de `N0` et quand la dernière référence du programme au nœud principal est détruite, les nœuds figurant dans la liste sont également détruits.  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[weak\_ptr::weak\_ptr](../Topic/weak_ptr::weak_ptr.md)|Construit un objet `weak_ptr`.|  
  
### Méthodes  
  
|||  
|-|-|  
|[weak\_ptr::element\_type](../Topic/weak_ptr::element_type.md)|Type de l'élément.|  
|[weak\_ptr::expired](../Topic/weak_ptr::expired.md)|Teste si la propriété a expiré.|  
|[weak\_ptr::lock](../Topic/weak_ptr::lock.md)|Obtient la propriété exclusive d'une ressource.|  
|[weak\_ptr::owner\_before](../Topic/weak_ptr::owner_before.md)|Retourne `true` si ce `weak_ptr` est classé avant le pointeur fourni \(ou est inférieur à celui\-ci\).|  
|[weak\_ptr::reset](../Topic/weak_ptr::reset.md)|Libère la ressource détenue.|  
|[weak\_ptr::swap](../Topic/weak_ptr::swap.md)|Échange deux objets `weak_ptr`.|  
|[weak\_ptr::use\_count](../Topic/weak_ptr::use_count.md)|Compte le nombres d'objets `shared_ptr` désignés.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)|Remplace la ressource détenue.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [shared\_ptr, classe](../standard-library/shared-ptr-class.md)