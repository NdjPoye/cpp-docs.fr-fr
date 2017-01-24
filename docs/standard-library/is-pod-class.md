---
title: "is_pod, classe | Microsoft Docs"
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
  - "std.tr1.is_pod"
  - "is_pod"
  - "std::tr1::is_pod"
  - "std.is_pod"
  - "std::is_pod"
  - "type_traits/std::is_pod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pod (classe) (TR1)"
  - "is_pod"
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_pod, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est POD.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_pod;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 `is_pod<Ty>::value` est `true` si le type `Ty` est Plain Old Data \(POD\).  Sinon, il est `false`.  
  
 Les types arithmétiques, les types énumération, les types pointeur et les pointeurs vers des types de membres sont des types POD.  
  
 Une version cv\-qualified d'un type POD est elle\-même un type POD.  
  
 Un tableau de POD est lui\-même POD.  
  
 Une structure ou une union, dont tous les membres de données non statiques sont POD, est elle\-même POD si elle n'a :  
  
-   aucun constructeur déclaré par l'utilisateur ;  
  
-   aucun membre de données non statiques privé ou protégé ;  
  
-   aucune classe de base ;  
  
-   aucune fonction virtuelle ;  
  
-   aucun membre de données non statiques de type référence ;  
  
-   aucun opérateur d'assignation de copie défini par l'utilisateur ;  
  
-   aucun destructeur défini par l'utilisateur.  
  
 Par conséquent, vous pouvez générer de manière récursive des structs et des tableaux POD qui contiennent des structs et des tableaux POD.  
  
## Exemple  
  
```  
// std_tr1__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct throws   
    {   
    throws() throw(int)   
        {   
        }   
  
    throws(const throws&) throw(int)   
        {   
        }   
  
    throws& operator=(const throws&) throw(int)   
        {   
        }   
  
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pod\<trivial\> \=\= true**  
**is\_pod\<int\> \=\= true**  
**is\_pod\<throws\> \=\= false**   
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)