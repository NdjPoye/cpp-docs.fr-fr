---
title: "Erreur du compilateur&#160;C2059 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2059"
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Erreur du compilateur&#160;C2059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : 'jeton'  
  
 Le jeton a causé une erreur de syntaxe.  
  
 L'exemple suivant génère un message d'erreur pour la ligne qui déclare `j`.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 Pour déterminer la cause de l'erreur, n'examinez pas seulement la ligne répertoriée dans le message d'erreur mais également les lignes au\-dessus.  Si l'examen des lignes ne donne aucun indice sur l'origine du problème, essayez de mettre en commentaires la ligne à laquelle on fait référence dans le message d'erreur et éventuellement plusieurs lignes au\-dessus.  
  
 Si le message d'erreur apparaît sur un symbole qui suit immédiatement une variable `typedef`, vérifiez que la variable est définie dans le code source.  
  
 Vous pouvez obtenir l'erreur C2059 si un symbole a une valeur nulle, comme cela peut se produire lorsque **\/D**`symbol`**\=** est utilisé pour compiler.  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 Un autre cas dans lequel l'erreur C2059 peut se produire est lorsque vous compilez une application spécifiant une structure dans les arguments par défaut d'une fonction.  La valeur par défaut d'un argument doit être une expression.  Une liste d'initialiseurs, telle que celle qui est utilisée pour initialiser une structure, n'est pas une expression.  Pour résoudre ce problème, définissez un constructeur pour effectuer l'initialisation requise.  
  
 L'exemple suivant génère C2059 :  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 L'erreur C2059 peut aussi apparaître si vous définissez une classe de modèles membres ou une fonction en dehors de la classe.  Pour plus d'informations, consultez [l'Article de la Base de Connaissances](http://support.microsoft.com/kb/241949).  
  
 L'erreur C2059 peut se produire en présence d'un cast de format incorrect.  
  
 L'exemple suivant génère l'erreur C2059 :  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 L'erreur C2059 peut également se produire si vous essayez de créer un nom d'espace de noms qui contient un point.  
  
 L'exemple suivant génère l'erreur C2059 :  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 L'erreur C2059 peut se produire lorsqu'un opérateur qui peut obtenir un nom \(`::`, `->`, et `.`\) doit être suivi du mot clé `template`, comme montré dans l'exemple suivant :  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 Par défaut, C\+\+ suppose que `AY::Rebind` n'est pas un modèle ; par conséquent, le `<` suivant est interprété comme un signe inférieur à.  Vous devez indiquer au compilateur explicitement que `Rebind` est un modèle afin qu'il puisse correctement analyser le crochet d'angle.  Pour corriger cette erreur, utilisez le mot clé `template` sur le nom dépendant du type, comme indiqué ici :  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```