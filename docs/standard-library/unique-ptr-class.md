---
title: "unique_ptr, classe | Microsoft Docs"
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
  - "unique_ptr"
  - "std.unique_ptr"
  - "std::unique_ptr"
  - "memory/std::unique_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_ptr (classe)"
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unique_ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stocke un pointeur vers un objet ou un tableau détenu.  L'objet\/tableau n'est détenu par aucun autre `unique_ptr`.  L'objet\/tableau est détruit quand `unique_ptr` est détruit.  
  
## Syntaxe  
  
```  
template< class T, class Del = default_delete<T> >  
    class unique_ptr {  
public:  
    unique_ptr( );  
    unique_ptr( nullptr_t Nptr );  
    explicit unique_ptr( pointer Ptr );  
    unique_ptr( pointer Ptr,  
        typename conditional<is_reference<Del>::value,   
            Del,  
            typename add_reference<const Del>::type>::type Deleter);  
    unique_ptr (pointer Ptr,  
        typename remove_reference<Del>::type&& Deleter);  
    unique_ptr (unique_ptr&& Right);  
    template<class T2, Class Del2> unique_ptr( unique_ptr<T2, Del2>&& Right );  
    unique_ptr( const unique_ptr& Right    ) = delete;  
    unique_ptr& operator=(const unique_ptr& Right     ) = delete;  
};  
  
```  
  
```  
//Specialization for arrays:  
template <class T, class D> class unique_ptr<T[], D>   
{   public:       
     typedef pointer;  
     typedef T element_type;  
     typedef D deleter_type;  
  
     constexpr unique_ptr() noexcept;  
     template <class U> explicit unique_ptr(U p) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     unique_ptr(unique_ptr&& u) noexcept;  
     constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }  
     template <class U, class E>  
       unique_ptr(unique_ptr<U, E>&& u) noexcept;  
  
     ~unique_ptr();  
  
     unique_ptr& operator=(unique_ptr&& u) noexcept;  
     template <class U, class E>  
       unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;  
     unique_ptr& operator=(nullptr_t) noexcept;  
  
     T& operator[](size_t i) const;  
     pointer get() const noexcept;  
     deleter_type& get_deleter() noexcept;  
     const deleter_type& get_deleter() const noexcept;  
     explicit operator bool() const noexcept;  
  
     pointer release() noexcept;  
     void reset(pointer p = pointer()) noexcept;  
     void reset(nullptr_t = nullptr) noexcept;  
     template <class U> void reset(U p) noexcept = delete;  
     void swap(unique_ptr& u) noexcept;  
  
    // disable copy from lvalue  
     unique_ptr(const unique_ptr&) = delete;  
     unique_ptr& operator=(const unique_ptr&) = delete;  
   };  
 }  
  
```  
  
#### Paramètres  
 `Right`  
 `unique_ptr`  
  
 `Nptr`  
 `rvalue` de type `std::nullptr_t`.  
  
 `Ptr`  
 `pointer`  
  
 `Deleter`  
 Fonction `deleter` liée à un `unique_ptr`.  
  
## Exceptions  
 Aucune exception n'est générée par `unique_ptr`.  
  
## Notes  
 La classe `unique_ptr` remplace `auto_ptr` et peut être utilisée comme élément des conteneurs STL.  
  
 Utilisez la fonction d'assistance [make\_unique](../Topic/make_unique.md) pour créer efficacement de nouvelles instances de `unique_ptr`.  
  
 `unique_ptr` gère de façon unique une ressource.  Chaque objet `unique_ptr` stocke un pointeur vers l'objet qu'il possède ou stocke un pointeur null.  Une ressource ne peut pas être détenue par plus d'un objet `unique_ptr`.  Quand l'objet `unique_ptr` qui possède une ressource particulière est détruit, la ressource est libérée.  Un objet `unique_ptr` peut être déplacé, mais pas copié.  Pour plus d'informations, consultez [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 La ressource est libérée par l'appel à un objet `deleter` stocké de type `Del` qui sait comment les ressources sont allouées pour un `unique_ptr` particulier.  L'objet `deleter` `default_delete``<T>` par défaut suppose que la ressource désignée par `_Ptr` est allouée à `new`, et qu'elle peut être libérée en appelant `delete _``Ptr`.  \(Une spécialisation partielle `unique_ptr<T[]>` gère les objets tableaux alloués à `new[]`, et possède le `deleter` `default_delete<T[]>` par défaut, spécialisé pour appeler delete\[\] `_Ptr`.\)  
  
 Le pointeur stocké vers une ressource détenue, `stored_ptr`, a le type `pointer`.  Il s'agit de `Del::pointer` s'il est défini, ou de `T *` dans le cas contraire.  L'objet `deleter` stocké `stored_deleter` n'occupe pas d'espace dans l'objet si le `deleter` est sans état.  Notez que `Del` peut être un type référence.  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[unique\_ptr::unique\_ptr](../Topic/unique_ptr::unique_ptr.md)|Il existe sept constructeurs pour `unique_ptr`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[deleter\_type](../Topic/deleter_type.md)|Synonyme pour le paramètre du modèle `Del`.|  
|[element\_type](../Topic/element_type.md)|Synonyme pour le paramètre du modèle `T``.`|  
|[pointeur](../Topic/pointer.md)|Synonyme pour `Del::pointer` s'il est défini ; sinon `T *`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[unique\_ptr::get](../Topic/unique_ptr::get.md)|Retourne `stored_ptr`.|  
|[unique\_ptr::get\_deleter](../Topic/unique_ptr::get_deleter.md)|Retourne une référence à `stored_deleter`.|  
|[unique\_ptr::release](../Topic/unique_ptr::release.md)|Stocke `pointer()` dans `stored_ptr` et retourne son contenu précédent.|  
|[unique\_ptr::reset](../Topic/unique_ptr::reset.md)|Libère la ressource détenue actuellement et accepte une nouvelle ressource.|  
|[unique\_ptr::swap](../Topic/unique_ptr::swap.md)|Échange la ressource et `deleter` avec l'objet `unique_ptr` fourni.|  
  
### Opérateurs  
  
|||  
|-|-|  
|`operator bool`|L'opérateur retourne une valeur d'un type qui peut être converti en `bool`.  Le résultat de la conversion en `bool` est `true` lorsque `get() != pointer()`, sinon `false`.|  
|`operator->`|La fonction membre retourne `stored_ptr``.`|  
|`operator*`|La fonction membre retourne\*`stored_ptr``.`|  
|[unique\_ptr operator\=](../Topic/unique_ptr%20operator=.md)|Affecte la valeur d'un objet `unique_ptr` \(ou un `pointer-type`\) à l'objet `unique_ptr` actuel.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<memory\>](../standard-library/memory.md)