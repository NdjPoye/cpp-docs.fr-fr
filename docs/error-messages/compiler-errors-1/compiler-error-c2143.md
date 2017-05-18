---
title: Erreur du compilateur C2143 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: faa9361da0091ec86628af19a03eadb133ea43cc
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2143"></a>Erreur du compilateur C2143
Erreur de syntaxe : absence de 'jeton1' avant 'jeton2'  
  
 Le compilateur attendait un jeton spécifique (autrement dit, un élément de langage autre qu’un espace blanc) et trouvé un autre jeton à la place.  
  
 Pour plus d’informations sur cette erreur lorsqu’il se produit lorsque vous utilisez un bloc try de fonction, consultez [l’article de la Base de connaissances 241706](http://support.microsoft.com/kb/241706).  
  
 Vérifier la [référence du langage C++](../../cpp/cpp-language-reference.md) pour déterminer où le code est syntaxiquement incorrecte. Étant donné que le compilateur peut signaler cette erreur après avoir rencontré la ligne qui provoque le problème, vérifiez à plusieurs lignes de code qui précèdent l’erreur.  
  
 L’erreur C2143 peut se produire dans différentes situations.  
  
 Il peut se produire lorsqu’un opérateur qui peut qualifier un nom (`::`, `->`, et `.`) doit être suivi par le mot clé `template`, comme dans cet exemple :  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Par défaut, C++ suppose que `Ty::PutFuncType` n’est pas un modèle ; par conséquent, les éléments suivants `<` est interprété comme un inférieur-signe.  Vous devez indiquer au compilateur explicitement que `PutFuncType` est un modèle afin de pouvoir analyser correctement le crochet pointu. Pour corriger cette erreur, utilisez le `template` (mot clé) sur le nom du type dépendants, comme illustré ici :  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 peut se produire lorsque **/clr** est utilisé et une `using` directive a une erreur de syntaxe :  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Il peut également se produire lorsque vous essayez de compiler un fichier de code source à l’aide de la syntaxe CLR sans utiliser également **/clr**:  
  
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
  
 Le premier caractère de non espace blanc qui suit une `if` instruction doit être une parenthèse ouvrante. Le compilateur ne peut pas traduire quoi :  
  
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
  
 C2143 peut se produire lorsqu’une accolade fermante, parenthèse ou point-virgule est manquant sur la ligne où l’erreur est détectée ou sur une des lignes juste au-dessus :  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Ou lorsqu’il existe une balise non valide dans une déclaration de classe :  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Ou lorsqu’une étiquette n’est pas attachée à une instruction. Si vous devez placer une étiquette par lui-même, par exemple, à la fin d’une instruction composée, attacher à une instruction null :  
  
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
  
 L’erreur peut se produire lorsqu’un appel non qualifié est fait à un type dans la bibliothèque C++ Standard :  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Ou il manque une `typename` mot clé :  
  
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
  
 Ou, si vous essayez de définir une instanciation explicite :  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 Dans un programme C, les variables doivent être déclarées au début de la fonction, et elles ne peuvent pas être déclarées après que la fonction exécute les instructions de déclaration non.  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  

