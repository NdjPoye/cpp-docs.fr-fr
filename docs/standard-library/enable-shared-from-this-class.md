---
title: "enable_shared_from_this, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.enable_shared_from_this"
  - "enable_shared_from_this"
  - "std.tr1.enable_shared_from_this"
  - "memory/std::tr1::enable_shared_from_this"
  - "std::tr1::enable_shared_from_this"
  - "tr1::enable_shared_from_this"
  - "std.enable_shared_from_this"
  - "memory/std::enable_shared_from_this"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enable_shared_from_this (classe)"
  - "enable_shared_from_this (classe) (TR1)"
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# enable_shared_from_this, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aide à générer un `shared_ptr`.  
  
## Syntaxe  
  
```  
template<class Ty>  
    class enable_shared_from_this {  
public:  
    shared_ptr<Ty> shared_from_this();  
    shared_ptr<const Ty> shared_from_this() const;  
  
protected:  
    enable_shared_from_this();  
    enable_shared_from_this(const enable_shared_from_this&);  
    enable_shared_from_this& operator=(const enable_shared_from_this&);  
    ~enable_shared_from_this();  
    };  
```  
  
#### Paramètres  
 `Ty`  
 Type contrôlé par le pointeur partagé.  
  
## Notes  
 Objets dérivés de `enable_shared_from_this` pouvez utiliser la `shared_from_this` méthodes dans des fonctions membres pour créer [shared\_ptr](../standard-library/shared-ptr-class.md) propriétaires de l’instance qui partagent la propriété avec existant `shared_ptr` propriétaires. Sinon, si vous créez un nouveau `shared_ptr` à l’aide de `this`, il se distingue d’existant `shared_ptr` propriétaires, ce qui peuvent entraîner non valide de références ou de l’objet à supprimer plusieurs fois.  
  
 Les constructeurs, le destructeur et l’opérateur d’assignation sont protégés afin d’éviter une mauvaise utilisation accidentelle. Le type d’argument template `Ty` doit être du type de la classe dérivée.  
  
 Pour obtenir un exemple d’utilisation, consultez [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md).  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)   
 [shared\_ptr, classe](../standard-library/shared-ptr-class.md)