---
title: "Erreur du compilateur C2143 | Microsoft Docs"
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
  - "C2143"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2143"
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2143
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : absence de 'jeton1' avant 'jeton2'  
  
 Le compilateur a attendu un jeton spécifique \(autrement dit, un élément de langage autre qu'un espace blanc\) et a trouvé à la place un autre jeton.  
  
 Pour plus d'informations sur cette erreur lorsqu'elle se produit pendant l'utilisation d'un bloc function\-try, consultez l' [Article de la Base de connaissances](http://support.microsoft.com/kb/241706).  
  
 Consultez le [Guide de référence du langage C\+\+](../../cpp/cpp-language-reference.md) pour déterminer si le code a une syntaxe incorrecte.  Vérifiez les quelques lignes de code qui précèdent l'erreur car le compilateur peut signaler cette erreur après avoir rencontré la ligne à l'origine du problème.  
  
 L'erreur C2143 peut se produire dans différentes situations.  
  
 Il peut se produire lorsqu'un opérateur qui peut obtenir un nom \(`::`, `->`, et `.`\) doit être suivi du mot clé `template`, comme dans l'exemple suivant :  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Par défaut, C\+\+ suppose que `Ty::PutFuncType` n'est pas un modèle ; par conséquent, le `<` suivant est interprété comme un signe inférieur à.  Vous devez indiquer au compilateur explicitement que `PutFuncType` est un modèle afin qu'il puisse correctement analyser le crochet d'angle.  Pour corriger cette erreur, utilisez le mot clé `template` sur le nom dépendant du type, comme indiqué ici :  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 peut se produire lorsque **\/clr** est utilisé et qu'une directive `using` contient une erreur de syntaxe :  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Cela peut également se produire lorsque vous essayez de compiler un fichier de code source en utilisant la syntaxe CLR sans utiliser aussi **\/clr** :  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 Le premier caractère autre qu'un espace blanc qui suit une instruction `if` doit être une parenthèse ouvrante.  Le compilateur ne peut pas traduire quoi que ce soit d'autre :  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143 peut se produire lorsqu'une accolade fermante, une parenthèse ou un point\-virgule est manquant sur la ligne où l'erreur est détectée ou sur l'une des lignes précédentes :  
  
```caml  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Ou lorsqu'il y a une balise invalide dans une déclaration de classe :  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Ou encore lorsqu'une étiquette n'est pas reliée à une instruction.  Si vous devez placer une étiquette seule \(par exemple, à la fin d'une instruction composée\), attachez\-la à une instruction null :  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 Cette erreur peut se produire lorsqu'un appel non qualifié est fait à un type de la bibliothèque C\+\+ standard :  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Ou il y a un mot clé absent dans `typename` :  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 Ou si vous essayez de définir une instanciation explicite :  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 Dans un programme C, les variables doivent être déclarées au début de la fonction et ne peuvent pas être déclarées après l'exécution d'instructions autres que des déclarations par la fonction.  
  
```c  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
  
```