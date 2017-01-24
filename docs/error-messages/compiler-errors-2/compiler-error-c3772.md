---
title: "Erreur du compilateur C3772 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3772"
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"name" : déclaration de modèle friend non valide  
  
 La déclaration d’une fonction friend d’une spécialisation de modèle de classe n’est pas autorisée. Vous ne pouvez pas déclarer de spécialisation explicite ou partielle d’un modèle de classe et déclarer, dans la même instruction, une fonction friend de cette spécialisation. L’espace réservé *name* identifie la déclaration non valide.  
  
### Pour corriger cette erreur  
  
-   Ne déclarez pas une fonction friend d’une spécialisation de modèle de classe.  
  
-   Si cela est adapté à votre application, déclarez une fonction friend du modèle de classe ou déclarez une fonction friend d’une spécialisation partielle ou explicite particulière.  
  
## Exemple  
 L’exemple de code suivant échoue, car il déclare une fonction friend d’une spécialisation partielle d’un modèle de classe.  
  
```  
// c3772.cpp // compile with: /c // A class template. template<class T> class A {}; // A partial specialization of the class template. template<class T> class A<T*> {}; // An explicit specialization. template<> class A<char>; class X { // Invalid declaration of a friend of a partial specialization. template<class T> friend class A<T*>; // C3772 // Instead, if it is appropriate for your application, declare a // friend of the class template. Consequently, all specializations // of the class template are friends: //    template<class T> friend class A; // Or declare a friend of a particular partial specialization: //    friend class A<int*>; // Or declare a friend of a particular explicit specialization: //    friend class A<char>; };  
```  
  
## Voir aussi  
 [Spécifications de modèle](../Topic/Template%20Specifications.md)   
 [Spécialisation partielle des modèles de classe](../../cpp/template-specialization-cpp.md)   
 [Spécialisation explicite des modèles de classe](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)