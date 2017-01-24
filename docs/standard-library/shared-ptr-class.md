---
title: "shared_ptr, classe | Microsoft Docs"
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
  - "shared_ptr"
  - "tr1::shared_ptr"
  - "memory/std::tr1::shared_ptr"
  - "std::tr1::shared_ptr"
  - "std.tr1.shared_ptr"
  - "tr1.shared_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared_ptr (classe)"
  - "shared_ptr (classe) (TR1)"
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
caps.latest.revision: 29
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shared_ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule un pointeur intelligent contenant des références autour d'un objet alloué dynamiquement.  
  
## Syntaxe  
  
```  
template<class Ty>  
   class shared_ptr {  
public:  
    typedef Ty element_type;  
  
    shared_ptr();  
    shared_ptr(nullptr_t);   
    shared_ptr(const shared_ptr& sp);  
    shared_ptr(shared_ptr&& sp);  
    template<class Other>  
        explicit shared_ptr(Other * ptr);  
    template<class Other, class D>  
        shared_ptr(Other * ptr, D dtor);  
    template<class D>  
        shared_ptr(nullptr_t, D dtor);  
    template<class Other, class D, class A>  
        shared_ptr(Other *ptr, D dtor, A alloc);  
    template<class D, class A>  
        shared_ptr(nullptr_t, D dtor, A alloc);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>&& sp);  
    template<class Other>  
        explicit shared_ptr(const weak_ptr<Other>& wp);  
    template<class Other>  
        shared_ptr(auto_ptr<Other>& ap);  
    template<class Other, class D>  
        shared_ptr(unique_ptr<Other, D>&& up);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp, Ty *ptr);  
    ~shared_ptr();  
    shared_ptr& operator=(const shared_ptr& sp);  
    template<class Other>   
        shared_ptr& operator=(const shared_ptr<Other>& sp);  
    shared_ptr& operator=(shared_ptr&& sp);  
    template<class Other>   
        shared_ptr& operator=(shared_ptr<Other>&& sp);  
    template<class Other>   
        shared_ptr& operator=(auto_ptr< Other >&& ap);  
    template <class Other, class D>   
        shared_ptr& operator=(const unique_ptr< Other, D>& up) = delete;  
    template <class Other, class D>  
        shared_ptr& operator=(unique_ptr<Other, D>&& up);  
    void swap(shared_ptr& sp);  
    void reset();  
    template<class Other>  
        void reset(Other *ptr);  
    template<class Other, class D>  
        void reset(Other *ptr, D dtor);  
    template<class Other, class D, class A>  
        void reset(Other *ptr, D dtor, A alloc);  
    Ty *get() const;  
    Ty& operator*() const;  
    Ty *operator->() const;  
    long use_count() const;  
    bool unique() const;  
    operator bool() const;  
  
    template<class Other>  
        bool owner_before(shared_ptr<Other> const& ptr) const;  
    template<class Other>  
        bool owner_before(weak_ptr<Other> const& ptr) const;  
    template<class D, class Ty>   
        D* get_deleter(shared_ptr<Ty> const& ptr);  
};  
  
```  
  
#### Paramètres  
 `Ty`  
 Type contrôlé par le pointeur partagé.  
  
 `Other`  
 Type contrôlé par le pointeur d'argument.  
  
 `ptr`  
 Pointeur à copier.  
  
 `D`  
 Type du suppresseur.  
  
 `A`  
 Type de l'allocateur.  
  
 `dtor`  
 Suppresseur.  
  
 `alloc`  
 Allocateur.  
  
 `sp`  
 Pointeur intelligent à copier ou déplacer.  
  
 `wp`  
 Pointeur faible à copier ou déplacer.  
  
 `ap`  
 Pointeur automatique à copier ou déplacer.  
  
 `up`  
 Pointeur unique à déplacer.  
  
## Notes  
 La classe de modèle décrit un objet qui utilise le décompte de références pour gérer les ressources.  Un objet `shared_ptr` contient en fait un pointeur vers la ressource qu'il possède ou contient un pointeur null.  Une ressource peut être détenue par plusieurs objets `shared_ptr`. Quand le dernier objet `shared_ptr` qui possède une ressource particulière est détruit, la ressource est libérée.  
  
 Un `shared_ptr` cesse de posséder une ressource quand il est réaffecté ou réinitialisé.  
  
 L'argument de modèle `Ty` peut être un type incomplet, sauf comme mentionné pour certaines fonctions membres.  
  
 Quand un objet `shared_ptr<Ty>` est construit à partir d'un pointeur de ressource de type `G*` ou à partir d'un `shared_ptr<G>`, le type de pointeur `G*` doit être convertible en `Ty*`.  Si ce n'est pas le cas, le code n'est pas compilé.  Exemple :  
  
```cpp  
class F {};  
class G : public F {};  
```  
  
```cpp  
  
#include <memory>  
  
using namespace std;  
  
shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*  
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>  
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*  
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>  
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>  
shared_ptr<int> sp5(new G); // error, G* not convertible to int*  
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>  
```  
  
 Un objet `shared_ptr` possède une ressource :  
  
-   s'il a été construit avec un pointeur vers cette ressource ;  
  
-   s'il a été construit à partir d'un objet `shared_ptr` qui possède cette ressource ;  
  
-   s'il a été construit à partir d'un objet [weak\_ptr, classe](../standard-library/weak-ptr-class.md) qui pointe vers cette ressource ; ou  
  
-   si la propriété de cette ressource lui a été affectée, soit avec [shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md), soit en appelant la fonction membre [shared\_ptr::reset](../Topic/shared_ptr::reset.md).  
  
 Les objets `shared_ptr` qui sont propriétaires d'une ressource partagent un bloc de contrôle.  Le bloc de contrôle contient :  
  
-   le nombre d'objets `shared_ptr` qui sont propriétaires de la ressource ;  
  
-   le nombre d'objets `weak_ptr` qui pointent vers la ressource ;  
  
-   le suppresseur de cette ressource, le cas échéant ;  
  
-   l'allocateur personnalisé pour le bloc de contrôle, le cas échéant.  
  
 Un objet `shared_ptr` qui est initialisé à l'aide d'un pointeur null a un bloc de contrôle et n'est pas vide.  Une fois qu'un objet `shared_ptr` a libéré une ressource, il n'en est plus propriétaire.  Une fois qu'un objet `weak_ptr` a libéré une ressource, il ne pointe plus vers cette ressource.  
  
 Quand le nombre d'objets `shared_ptr` propriétaires d'une ressource devient égal à zéro, la ressource est libérée, soit en étant supprimée, soit en passant son adresse à un suppresseur, selon la façon dont la propriété de la ressource a été créée initialement.  Quand le nombre d'objets `shared_ptr` propriétaires d'une ressource est égal à zéro et que le nombre d'objets `weak_ptr` qui pointent vers cette ressource est égal à zéro, le bloc de contrôle est libéré, à l'aide de l'allocateur personnalisé du bloc de contrôle s'il en a un.  
  
 Un objet `shared_ptr` vide ne possède pas de ressource et n'a aucun bloc de contrôle.  
  
 Un suppresseur est un objet de fonction qui a une fonction membre `operator()`.  Son type doit être constructible par copie et son constructeur de copie et son destructeur ne doivent pas lever d'exceptions.  Il accepte un paramètre, l'objet à supprimer.  
  
 Certaines fonctions acceptent une liste d'arguments qui définit les propriétés de l'objet `shared_ptr<Ty>` ou `weak_ptr<Ty>` résultant.  Vous pouvez spécifier une telle liste d'arguments de plusieurs façons :  
  
 aucun argument : l'objet résultant est un objet `shared_ptr` vide ou un objet `weak_ptr` vide.  
  
 `ptr` : un pointeur de type `Other*` vers la ressource à gérer.  `Ty` doit être un type complet.  Si la fonction échoue \(car le bloc de contrôle ne peut pas être alloué\), elle évalue l'expression `delete ptr`.  
  
 `ptr, dtor` : un pointeur de type `Other*` vers la ressource à gérer et un suppresseur pour cette ressource.  Si la fonction échoue \(car le bloc de contrôle ne peut pas être alloué\), elle appelle `dtor(ptr)`, qui doit être défini correctement.  
  
 `ptr, dtor, alloc` : un pointeur de type `Other*` vers la ressource à gérer, un suppresseur pour cette ressource et un allocateur pour gérer tout stockage qui doit être alloué et libéré.  Si la fonction échoue \(car le bloc de contrôle ne peut pas être alloué\), elle appelle `dtor(ptr)`, qui doit être défini correctement.  
  
 `sp` : un objet `shared_ptr<Other>` propriétaire de la ressource à gérer.  
  
 `wp` : un objet `weak_ptr<Other>` qui pointe vers la ressource à gérer.  
  
 `ap` : un objet `auto_ptr<Other>` qui contient un pointeur vers la ressource à gérer.  Si la fonction réussit, elle appelle `ap.release()` ; sinon, elle laisse `ap` inchangé.  
  
 Dans tous les cas, le type de pointeur `Other*` doit être convertible en `Ty*`.  
  
## Sécurité des threads  
 Plusieurs threads peuvent lire et écrire différents objets `shared_ptr` simultanément, même quand les objets sont des copies qui partagent la propriété.  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[shared\_ptr::shared\_ptr](../Topic/shared_ptr::shared_ptr.md)|Construit un objet `shared_ptr`.|  
|[shared\_ptr::~shared\_ptr](../Topic/shared_ptr::~shared_ptr.md)|Détruit un `shared_ptr`.|  
  
### Méthodes  
  
|||  
|-|-|  
|[shared\_ptr::element\_type](../Topic/shared_ptr::element_type.md)|Type d'un élément.|  
|[shared\_ptr::get](../Topic/shared_ptr::get.md)|Obtient l'adresse de la ressource détenue.|  
|[shared\_ptr::owner\_before](../Topic/shared_ptr::owner_before.md)|Retourne true si ce `shared_ptr` est classé avant le pointeur fourni \(ou est inférieur à celui\-ci\).|  
|[shared\_ptr::reset](../Topic/shared_ptr::reset.md)|Remplacer la ressource détenue.|  
|[shared\_ptr::swap](../Topic/shared_ptr::swap.md)|Permute deux objets `shared_ptr`.|  
|[shared\_ptr::unique](../Topic/shared_ptr::unique.md)|Teste si la ressource détenue est unique.|  
|[shared\_ptr::use\_count](../Topic/shared_ptr::use_count.md)|Compte le nombre de propriétaires de ressources.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[shared\_ptr::operator, \(type booléen\)](../Topic/shared_ptr::operator%20boolean-type.md)|Teste si une ressource détenue existe.|  
|[shared\_ptr::operator\*](../Topic/shared_ptr::operator*.md)|Obtient la valeur désignée.|  
|[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)|Remplace la ressource détenue.|  
|[shared\_ptr::operator\-\>](../Topic/shared_ptr::operator-%3E.md)|Obtient un pointeur vers la valeur désignée.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [weak\_ptr, classe](../standard-library/weak-ptr-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)