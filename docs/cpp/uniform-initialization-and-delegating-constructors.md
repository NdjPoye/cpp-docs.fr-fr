---
title: "Constructeurs d&#39;initialisation uniforme et de d&#233;l&#233;gation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Constructeurs d&#39;initialisation uniforme et de d&#233;l&#233;gation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En C\+\+ récent, vous pouvez utiliser *Initialisation d'accolades* pour tout type, sans signe égal.  En outre, utilisez des constructeurs qui délèguent pour simplifier votre code lorsque vous avez plusieurs constructeurs qui effectuent le travail similaires.  
  
## Initialisation d'accolades  
 Utilisez l'initialisation d'accolades pour une classe, un struct, ou union.  Si un type a un constructeur par défaut, implicitement ou explicitement déclaré, utilisez l'initialisation par défaut d'accolade \(avec accolades vide\).  Par exemple, la classe suivante peut être initialisée à l'aide des deux valeurs par défaut et de l'initialisation non définie par défaut d'accolades :  
  
```cpp  
#include <string>  
using namespace std;  
  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}  
double m_double;  
string m_string;  
};  
  
int main()  
{  
    class_a c1{};  
    class_a c1_1;  
  
    class_a c2{ "ww" };  
    class_a c2_1("xx");  
  
    // order of parameters is the same as the constructor  
    class_a c3{ "yy", 4.4 };  
    class_a c3_1("zz", 5.5);  
}  
  
```  
  
 Si une classe a des constructeurs non définis par défaut, l'ordre dans lequel les membres de classe s'affichent dans l'initialiseur d'accolades est l'ordre dans lequel les paramètres correspondants apparaissent dans le constructeur, pas l'ordre dans lequel les membres sont déclarés \(comme avec `class_a` dans l'exemple précédent\).  Sinon, si le type a aucun constructeur déclaré, l'ordre dans lequel les membres apparaissent dans l'initialiseur d'accolades n'est celui dans lequel ils sont déclarés ; Dans ce cas, initialisez autant des membres publics comme vous le souhaitez, mais vous ne pouvez ignorer aucun membre.  L'exemple suivant indique l'ordre utilisé dans l'initialisation d'accolades lorsque aucun constructeur n'est déclaré :  
  
```cpp  
class class_d {  
public:  
    float m_float;  
    string m_string;  
    wchar_t m_char;  
};  
  
int main()  
{  
    class_d d1{};  
    class_d d1{ 4.5 };  
    class_d d2{ 4.5, "string" };  
    class_d d3{ 4.5, "string", 'c' };  
  
    class_d d4{ "string", 'c' }; // compiler error  
    class_d d5("string", 'c', 2.0 }; // compiler error  
}   
```  
  
 Si le constructeur par défaut est déclaré explicitement mais marqué comme supprimé, l'initialisation d'accolades par défaut ne peut pas être utilisée:  
  
```cpp  
class class_f {  
public:  
    class_f() = delete;  
    class_f(string x): m_string { x } {}  
    string m_string;  
};  
int main()  
{  
    class_f cf{ "hello" };  
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function  
}  
```  
  
 Utilisez l'initialisation d'accolades partout où vous devez généralement initialisation\- par exemple, un paramètre de fonction ou une valeur de retour, ou avec le mot clé `new`:  
  
```cpp  
class_d* cf = new class_d{4.5};  
kr->add_d({ 4.5 });  
return { 4.5 };  
  
```  
  
## constructeurs d'initializer\_list  
 La [initializer\_list Class](../standard-library/initializer-list-class.md) représente une liste d'objets d'un type spécifié qui peut être utilisé dans un constructeur, et dans d'autres contextes.  Construisez une initializer\_list à l'aide de l'initialisation d'accolades:  
  
```cpp  
initializer_list<int> int_list{5, 6, 7};  
```  
  
> [!IMPORTANT]
>  Pour utiliser cette classe, vous devez inclure l'en\-tête [\<initializer\_list\>](../standard-library/initializer-list.md).  
  
 Une `initializer_list` peut être copié.  Dans ce cas, les membres de la nouvelle liste sont des références aux membres de la liste d'origine:  
  
```cpp  
initializer_list<int> ilist1{ 5, 6, 7 };  
initializer_list<int> ilist2( ilist1 );  
if (ilist1.begin() == ilist2.begin())  
    cout << "yes" << endl; // expect "yes"  
  
```  
  
 Les classes de conteneur standard de bibliothèque, et également `string`, `wstring`, et `regex`, possèdent des constructeurs `initializer_list`.  Les exemples suivants montrent comment effectuer l'initialisation d'accolades avec ces constructeurs :  
  
```cpp  
vector<int> v1{ 9, 10, 11 };   
map<int, string> m1{ {1, "a"}, {2, "b"} };  
string s{ 'a', 'b', 'c' };   
regex rgx{'x', 'y', 'z'};   
```  
  
## Constructeurs qui effectuent une délégation  
 De nombreuses classes ont plusieurs constructeurs qui font des choses semblables\- par exemple, valider les paramètres :  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c() {}  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) {   
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) {  
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
    }  
};  
```  
  
 Vous pouvez réduire code répétitif en ajoutant une fonction qui réalise toute la validation, mais il est plus facile de comprendre et gérer le code pour `class_c` si un constructeur peut déléguer partie du travail à un autre.  Pour ajouter la délégation des constructeurs, utilisez la syntaxe `constructor (. . .) : constructor (. . .)`:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) : class_c(my_max) {   
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
}  
};  
int main() {  
  
    class_c c1{ 1, 3, 2 };  
}  
  
```  
  
 Alors que vous parcourez l'exemple précédent, notez que les appels de `class_c(int, int, int)` du constructeur appellent d'abord le constructeur `class_c(int, int)`, qui appelle ensuite `class_c(int)`.  Chacun des constructeurs effectue uniquement le travail qui n'est pas effectué par les autres constructeurs.  
  
 Le premier constructeur appelé initialise l'objet afin que tous ses membres soient initialisées à ce stade.  Vous ne pouvez pas effectuer l'initialisation de membre d'un constructeur qui délègue à un autre constructeur, comme indiqué ci\-après :  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    // member initialization here, no delegate  
    class_a(string str) : m_string{ str } {}  
  
    //can’t do member initialization here  
    // error C3511: a call to a delegating constructor shall be the only member-initializer  
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}  
  
    // only member assignment  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string;  
};  
  
```  
  
 L'exemple suivant illustre l'utilisation des initialiseurs de donnée membre non statique.  Notez que si un constructeur initialise également une donnée membre donnée, l'initialiseur membre est substitué :  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };  
};  
  
int main() {  
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"  
    int y = 4;  
}  
```  
  
 La syntaxe de délégation de constructeur n'empêché pas la conception accidentelle des appels Constructor2 du constructeur recursion\-Constructor1 qui appelle Constructor1\-and qu'aucune erreur n'est levée jusqu'à ce qu'il y ait un dépassement de capacité de la pile.  Il est de votre responsabilité d'éviter des cycles.  
  
```cpp  
class class_f{  
public:  
    int max;  
    int min;  
  
    // don't do this  
    class_f() : class_f(6, 3){ }  
    class_f(int my_max, int my_min) : class_f() { }  
};  
```