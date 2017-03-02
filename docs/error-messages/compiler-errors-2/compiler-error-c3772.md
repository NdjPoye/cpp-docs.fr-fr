---
title: "C3772 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 7bf4fc0d7e80d2bd77343ee43c31dc74b93c97de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3772"></a>Erreur du compilateur C3772
"name" : déclaration de modèle friend non valide  
  
La déclaration d’une fonction friend d’une spécialisation de modèle de classe n’est pas autorisée. Vous ne pouvez pas déclarer de spécialisation explicite ou partielle d’un modèle de classe et déclarer, dans la même instruction, une fonction friend de cette spécialisation. L’espace réservé *name* identifie la déclaration non valide.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Ne déclarez pas une fonction friend d’une spécialisation de modèle de classe.  
  
-   Si cela est adapté à votre application, déclarez une fonction friend du modèle de classe ou déclarez une fonction friend d’une spécialisation partielle ou explicite particulière.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant échoue, car il déclare une fonction friend d’une spécialisation partielle d’un modèle de classe.  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
[Modèles](../../cpp/templates-cpp.md)   
[Spécialisation de modèle](../../cpp/template-specialization-cpp.md)   

