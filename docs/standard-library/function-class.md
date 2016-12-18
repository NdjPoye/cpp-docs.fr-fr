---
title: "function, classe | Microsoft Docs"
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
  - "functional/std::tr1::function"
  - "std.tr1.function"
  - "std::tr1::function"
  - "function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "function (classe) (TR1)"
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wrapper pour un objet appelable.  
  
## Syntaxe  
  
```cpp  
template<class Fty>  
   class function  // Fty of type Ret(T1, T2, ..., TN)  
   : public unary_function<T1, Ret>       // when Fty is Ret(T1)  
   : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)  
   {  
public:  
   typedef Ret result_type;  
  
   function();  
   function(nullptr_t);  
   function(const function& _Right);  
   template<class Fty2>  
      function(Fty2 fn);  
   template<class Fty2, class Alloc>  
       function (reference_wrapper<Fty2>, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       void assign (Fty2, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       assign (reference_wrapper<Fty2>, const Alloc& _Ax);  
```  
  
```cpp  
function& operator=(nullptr_t);  
function& operator=(const function&);  
template<class Fty2>  
   function& operator=(Fty2);  
template<class Fty2>  
   function& operator=(reference_wrapper<Fty2>);  
void swap(function&);  
  
explicit operator bool() const;  
result_type operator()(T1, T2, ....., TN) const;  
  
const std::type_info& target_type() const;  
template<class Fty2>  
   Fty2 *target();  
template<class Fty2>  
   const Fty2 *target() const;  
```  
  
```cpp  
   template<class Fty2>  
      void operator==(const Fty2&) const = delete;  
   template<class Fty2>  
      void operator!=(const Fty2&) const = delete;  
};  
```  
  
#### Paramètres  
 `Fty`  
 Le type de fonction à inclure.  
  
 `_Ax`  
 La fonction d'allocateur.  
  
## Notes  
 La classe de modèle est un wrapper d'appel dont la signature appelante est `Ret(T1, T2, ..., TN)`.  Vous l'utilisez pour encadrer divers objets appelabmes dans un wrapper uniforme.  
  
 Certaines fonctions membres prennent un opérande qui désigne l'objet cible souhaité.  Vous pouvez spécifier cet opérande de plusieurs façons.  
  
 `fn` \-\- l'objet appelable `fn`; après l'appel l'objet `function` contiens une copie de `fn`  
  
 `fnref` \-\- l'objet appelable nommée par `fnref.get()`; après l'appel l'objet `function` contiens une référence à `fnref.get()`  
  
 `right` \-\- l'objet appelable, s'il existe, détenu par l'objet `function` object `right`  
  
 `npc` \-\- un pointeur null ; après l'appel l'objet `function` est vide  
  
 Dans tous les cas, `INVOKE(f, t1, t2, ..., tN)`, où `f` est l'objet appelable et `t1, t2, ..., tN` sont des lvalues les types `T1, T2, ..., TN` respectivement, doivent être bien formées et, si `Ret` n'est pas vide, doivent pouvoir être converti en `Ret`.  
  
 Un objet vide `function` ne conserve pas un objet appelable ou une référence à un objet appelable.  
  
### Constructeurs  
  
|||  
|-|-|  
|[function::function](../Topic/function::function.md)|Construit un wrapper soit vide ou qui enregistre un objet appelable de type arbitraire avec une signature fixe.|  
  
### Typedef  
  
|||  
|-|-|  
|[function::result\_type](../Topic/function::result_type.md)|Le type de retour de l'objet appelable stocké.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[function::assign](../Topic/function::assign.md)|Affecte un objet appelable à cet objet de la fonction.|  
|[function::swap](../Topic/function::swap.md)|Interverti deux objets appelables.|  
|[function::target](../Topic/function::target.md)|Teste si l'objet appelable stocké est appelable comme spécifié.|  
|[function::target\_type](../Topic/function::target_type.md)|Obtient les informations de type de l'objet appelable.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[function::operator non spécifié](../Topic/function::operator%20unspecified.md)|Teste si l'objet appelable existe.|  
|[function::operator\(\)](../Topic/function::operator\(\).md)|Appelle un objet appelable.|  
|[function::operator\=](../Topic/function::operator=.md)|Remplace l'objet appelable stocké.|  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [mem\_fn, fonction](../Topic/mem_fn%20Function.md)   
 [reference\_wrapper, classe](../standard-library/reference-wrapper-class.md)