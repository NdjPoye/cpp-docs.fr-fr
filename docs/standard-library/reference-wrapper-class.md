---
title: "reference_wrapper, classe | Microsoft Docs"
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
  - "std.tr1.reference_wrapper"
  - "tr1.reference_wrapper"
  - "reference_wrapper"
  - "tr1::reference_wrapper"
  - "xrefwrap/std::tr1::reference_wrapper"
  - "std::tr1::reference_wrapper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference_wrapper (classe)"
  - "reference_wrapper (classe) (TR1)"
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# reference_wrapper, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule une référence.  
  
## Syntaxe  
  
```  
template<class Ty>  
    class reference_wrapper  
    : public unary_function<T1, Ret>        // see below  
    : public binary_function<T1, T2, Ret>   // see below  
    {  
public:  
    typedef Ty type;  
    typedef T0 result_type;                 // see below  
  
    reference_wrapper(Ty&);  
  
    Ty& get() const;  
    operator Ty&() const;  
    template<class T1, class T2, ..., class TN>  
        typename result_of<T(T1, T2, ..., TN)>::type  
        operator()(T1&, T2&, ..., TN&);  
  
private:  
    Ty *ptr; // exposition only  
    };  
```  
  
## Notes  
 Un `reference_wrapper<Ty>` est assignable et constructible par copie. Il contient un pointeur vers un objet de type `Ty`.  
  
 Un `reference_wrapper<Ty>` de spécialisation est dérivé de `std::unary_function<T1, Ret>` \(et définit donc le type imbriqué `result_type` comme synonyme de `Ret` et le type imbriqué `argument_type` comme synonyme de `T1`\) uniquement si le type `Ty` est :  
  
 un type de fonction ou un pointeur vers un type de fonction acceptant un argument de type `T1` et retournant `Ret` ; ou  
  
 un pointeur vers une fonction membre `Ret T::f() cv`, où `cv` représente les cv\-qualifiers de la fonction membre ; le type `T1` est `cv` `T*` ; ou  
  
 un type de classe dérivé de `unary_function<T1, Ret>`.  
  
 Un `reference_wrapper<Ty>` de spécialisation est dérivé de `std::binary_function<T1, T2, Ret>` \(et définit donc le type imbriqué `result_type` comme synonyme de `Ret`, le type imbriqué `first_argument_type` comme synonyme de `T1` et le type imbriqué `second_argument_type` comme synonyme de `T2`\) uniquement si le type `Ty` est :  
  
 un type de fonction ou un pointeur vers un type de fonction acceptant deux arguments de types `T1` et `T2` retournant `Ret` ; ou  
  
 un pointeur vers une fonction membre `Ret T::f(T2) cv`, où `cv` représente les cv\-qualifiers de la fonction membre ; le type `T1` est `cv` `T*` ; ou  
  
 un type de classe dérivé de `binary_function<T1, T2, Ret>`.  
  
### Constructeurs  
  
|||  
|-|-|  
|[reference\_wrapper::reference\_wrapper](../Topic/reference_wrapper::reference_wrapper.md)|Construit un objet `reference_wrapper`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[reference\_wrapper::result\_type](../Topic/reference_wrapper::result_type.md)|Type de résultat faible de la référence encapsulée.|  
|[reference\_wrapper::type](../Topic/reference_wrapper::type.md)|Type de la référence encapsulée.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[reference\_wrapper::get](../Topic/reference_wrapper::get.md)|Obtient la référence encapsulée.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[reference\_wrapper::operator Ty&](../Topic/reference_wrapper::operator%20Ty&.md)|Obtient un pointeur vers la référence encapsulée.|  
|[reference\_wrapper::operator\(\)](../Topic/reference_wrapper::operator\(\).md)|Appelle la référence encapsulée.|  
  
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [cref, fonction](../Topic/cref%20Function.md)   
 [ref, fonction](../Topic/ref%20Function.md)