---
title: "auto_ptr, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::auto_ptr"
  - "std.auto_ptr"
  - "auto_ptr"
  - "memory/std::auto_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_ptr (classe)"
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# auto_ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule un pointeur intelligent autour d'une ressource qui garantit que celle\-ci est supprimée automatiquement quand le contrôle quitte un bloc.  
  
 La classe `unique_ptr` plus performante remplace `auto_ptr`.  Pour plus d'informations, consultez [unique\_ptr, classe](../standard-library/unique-ptr-class.md).  
  
 Pour plus d'informations sur `throw()` et sur la gestion des exceptions, consultez [Spécifications d'exception \(throw\)](../cpp/exception-specifications-throw-cpp.md).  
  
## Syntaxe  
  
```  
template<class Type>  
    class auto_ptr {  
public:  
    typedef Type element_type;  
    explicit auto_ptr(Type *_Ptr = 0) throw();  
    auto_ptr(auto_ptr<Type>& _Right) throw();  
    template<class Other>  
        operator auto_ptr<Other>() throw();  
    template<class Other>  
        auto_ptr<Type>& operator=(auto_ptr<Other>& _Right) throw();  
    template<class Other>  
        auto_ptr(auto_ptr<Other>& _Right);  
    auto_ptr<Type>& operator=(auto_ptr<Type>& _Right);  
    ~auto_ptr();  
    Type& operator*() const throw();  
    Type *operator->()const throw();  
    Type *get() const throw();  
    Type *release()throw();  
    void reset(Type *_Ptr = 0);  
};  
```  
  
#### Paramètres  
 `_Right`  
 `auto_ptr` à partir duquel obtenir une ressource existante.  
  
 `_Ptr`  
 Pointeur spécifié pour remplacer le pointeur stocké.  
  
## Notes  
 La classe de modèle décrit un pointeur intelligent, appelé `auto_ptr,` pour un objet alloué.  Le pointeur doit avoir la valeur null ou désigner un objet alloué par `new`.  Le `auto_ptr` transfère la propriété si sa valeur stockée est assignée à un autre objet.  \(Il remplace la valeur stockée après un transfert avec un pointeur null.\) Le destructeur de `auto_ptr<Type>` supprime l'objet alloué.  Le `auto_ptr<Type>` garantit qu'un objet alloué est supprimé automatiquement quand le contrôle quitte un bloc, même suite à la levée d'une exception.  Vous ne devez pas construire deux objets `auto_ptr<Type>` qui possèdent le même objet.  
  
 Vous pouvez passer un objet `auto_ptr<Type>` par valeur en tant qu'argument à un appel de fonction.  Un `auto_ptr` ne peut pas être un élément d'un conteneur de bibliothèque STL.  Vous ne pouvez pas gérer de manière fiable une séquence d'objets `auto_ptr<Type>` avec un conteneur de bibliothèque STL.  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[auto\_ptr](../Topic/auto_ptr::auto_ptr.md)|Constructeur des objets de type `auto_ptr`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/auto_ptr::element_type.md)|Le type est un synonyme du paramètre de modèle `Type`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[get](../Topic/auto_ptr::get.md)|La fonction membre retourne le pointeur stocké `myptr`.|  
|[release](../Topic/auto_ptr::release.md)|Le membre remplace le pointeur stocké `myptr` par un pointeur null et il retourne le pointeur stocké précédemment.|  
|[reset](../Topic/auto_ptr::reset.md)|La fonction membre évalue l'expression `delete myptr`, mais uniquement si la valeur de pointeur stocké `myptr` change suite à l'appel de fonction.  Elle remplace ensuite le pointeur stocké par `ptr`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=](../Topic/auto_ptr::operator=.md)|Opérateur d'assignation qui transfère la propriété d'un objet `auto_ptr` à un autre.|  
|[operator\*](../Topic/auto_ptr::operator*.md)|Opérateur de déréférencement pour les objets de type `auto_ptr`.|  
|[operator\-\>](../Topic/auto_ptr::operator-%3E.md)|Opérateur pour autoriser l'accès aux membres.|  
|[operator auto\_ptr\<Other\>](../Topic/auto_ptr::operator%20auto_ptr%3COther%3E.md)|Effectue un cast d'un type de `auto_ptr` vers un autre type de `auto_ptr`.|  
|[operator auto\_ptr\_ref\<Other\>](../Topic/auto_ptr::operator%20auto_ptr_ref%3COther%3E.md)|Effectue un cast d'un `auto_ptr` vers un `auto_ptr_ref`.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique\_ptr, classe](../standard-library/unique-ptr-class.md)