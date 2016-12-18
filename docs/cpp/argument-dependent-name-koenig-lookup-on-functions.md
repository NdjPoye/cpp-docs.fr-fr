---
title: "Recherche de nom qui d&#233;pend de l&#39;argument (Koenig) sur les fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "recherche qui dépend de l'argument (C++)"
  - "Koenig (recherche)"
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recherche de nom qui d&#233;pend de l&#39;argument (Koenig) sur les fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur peut utiliser la recherche de nom dépendante d'un argument pour rechercher la définition d'un appel de fonction non qualifié.  La recherche de nom dépendante d'un argument est également appelée recherche Koenig.  Le type de chaque argument dans un appel de fonction est défini dans une hiérarchie d'espaces de noms, de classes, de structures, d'unions ou de modèles.  Lorsque vous spécifiez un appel de fonction [postfix](../cpp/postfix-expressions.md), le compilateur recherche la définition de fonction dans la hiérarchie associée à chaque type d'argument.  
  
## Exemple  
 Dans l'exemple, le compilateur note que la fonction `f()` prend un argument `x`.  L'argument `x` est de type `A::X`, qui est défini dans l'espace de noms `A`.  Le compilateur recherche l'espace de noms `A` et trouve une définition pour la fonction `f()` qui prend un argument de type `A::X`.  
  
```  
// argument_dependent_name_koenig_lookup_on_functions.cpp  
namespace A  
{  
   struct X  
   {  
   };  
   void f(const X&)  
   {  
   }  
}  
int main()  
{  
// The compiler finds A::f() in namespace A, which is where   
// the type of argument x is defined. The type of x is A::X.  
   A::X x;  
   f(x);     
}  
```  
  
## Voir aussi  
 [Conformité améliorée du compilateur Visual C\+\+ .NET 2003](../misc/visual-cpp-dotnet-2003-enhanced-compiler-conformance.md)