---
title: "Erreur du compilateur C2797 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2797"
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'initialisation de la liste dans la liste d'initialiseur membre ou l'initialiseur membre de données non statique n'est pas implémenté.  
  
 Le compilateur C\+\+ de Visual Studio n'implémente pas l'initialisation de la liste dans une liste d'initialiseur membre ou un initialiseur de membre de données non statique.  Avant Visual Studio 2013 Update 3, une conversion en appel de fonction se produisait en mode silencieux, ce qui pouvait occasionner une génération de code incorrect.  Visual Studio 2013 Update 3 signale cela comme une erreur.  
  
 Cet exemple génère C2797 :  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 Cet exemple génère aussi C2797 :  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 Pour résoudre ce problème, vous pouvez utiliser une construction explicite de listes internes.  Par exemple :  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 Si vous n'avez pas besoin de l'initialisation de la liste :  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 \(Le compilateur de Visual Studio 2013 effectue cette tâche implicitement avant Visual Studio 2013 Update 3.\)