---
title: Constructeurs (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ece3414dbc7f4d362fa7dcc6f060e408b50e54e6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="constructors-c"></a>Constructeurs (C++)
Un constructeur est un type de fonction membre qui initialise une instance de sa classe. Un constructeur porte le même nom que la classe et n'a aucune valeur de retour. Un constructeur peut avoir un nombre quelconque de paramètres et une classe peut avoir un nombre quelconque de constructeurs surchargés. Les constructeurs peuvent avoir n'importe quelle accessibilité : publique, protégée ou privée. Si vous ne définissez pas de constructeurs, le compilateur génère un constructeur par défaut qui n'accepte aucun paramètre ; vous pouvez substituer ce comportement en déclarant un constructeur par défaut comme supprimé.  
  
## <a name="in-this-topic"></a>Dans cette rubrique  
  
-   [Ordre de Construction](#order_of_construction)  
  
-   [Listes de membres](#member_lists)  
  
-   [Constructeurs explicites](#explicit_constructors)  
  
-   [Constructeurs par défaut](#default_constructors)  
  
-   [Copier et déplacer des constructeurs](#copy_and_move_constructors)  
  
-   [Constructeurs explicitement utilisés par défaut et supprimés](#explicitly_defaulted_and_deleted_constructors)  
  
-   [Constructeurs de Classes dérivées](#constructors_in_derived_classes)  
  
-   [Fonctions virtuelles dans les constructeurs](#virtual_functions_in_constructors)  
  
-   [Constructeurs et Classes composites](#constructors_in_composite_classes)  
  
-   [Constructeurs de délégation](#delegating_constructors)  
  
-   [Constructeurs d’héritage (C ++ 11)](#inheriting_constructors)  
  
-   [Règles de déclaration des constructeurs](#rules_for_declaring_constructors)  
  
-   [Appel explicite des constructeurs](#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a>Ordre de Construction  
 Un constructeur effectue son travail dans l'ordre suivant :  
  
1.  Il appelle les constructeurs membres et de classe de base dans l'ordre de déclaration.  
  
2.  Si la classe est dérivée de classes de base virtuelles, il initialise les pointeurs de base virtuels de l'objet.  
  
3.  Si la classe possède ou hérite des fonctions virtuelles, il initialise les pointeurs de fonction virtuelle de l'objet. Les pointeurs de fonction virtuelle pointent sur la table de fonctions virtuelles de la classe pour permettre la liaison correcte des appels de fonction virtuelle au code.  
  
4.  Il exécute le code dans son corps de fonction.  
  
 L'exemple suivant montre l'ordre dans lequel les constructeurs de classe de base et membres sont appelés dans le constructeur pour une classe dérivée. D'abord, le constructeur de base est appelé, puis les membres de classe de base sont initialisés dans l'ordre dans lequel ils apparaissent dans la déclaration de classe, puis le constructeur dérivé est appelé.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 Voici la sortie :  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 Si un constructeur lève une exception, l'ordre de destruction est l'inverse de l'ordre de construction :  
  
1.  Le code dans le corps de la fonction constructeur est déroulé.  
  
2.  Les objets de classe de base et membres sont détruits dans l'ordre inverse de déclaration.  
  
3.  Si le constructeur ne délègue pas, tous les membres et objets de classe de base entièrement construits sont détruits. Toutefois, l'objet lui-même n'étant pas complètement construit, le destructeur n'est pas exécuté.  
  
##  <a name="member_lists"></a>Listes de membres  
 Initialisez les membres de classe à partir des arguments de constructeur à l’aide d’une liste d’initialiseurs membres. Cette méthode utilise *une initialisation directe*, qui est plus efficace que l’utilisation d’opérateurs d’assignation dans le corps du constructeur.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 Créez un objet Box :  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a>Constructeurs explicites  
 Si une classe a un constructeur avec un paramètre unique, ou si tous les paramètres sauf un ont une valeur par défaut, le type de paramètre peut être implicitement converti en type de classe. Par exemple, si la classe `Box` a un constructeur semblable au suivant :  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Il est possible d'initialiser un objet Box comme suit :  
  
```  
Box b = 42;  
```  
  
 Ou de passer une valeur int à une fonction qui accepte un objet Box :  
  
```  
class ShippingOrder  
{  
public:  
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}  
  
private:  
    Box m_box;  
    double m_postage;  
}  
//elsewhere...  
    ShippingOrder so(42, 10.8);  
  
```  
  
 Ces conversions peuvent être utiles dans certains cas mais, le plus souvent, elles peuvent entraîner des erreurs subtiles mais graves dans votre code. En règle générale, vous devez utiliser le mot clé `explicit` sur un constructeur (et des opérateurs définis par l'utilisateur) afin d'éviter ce genre de conversion de type implicite :  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Si le constructeur est explicite, cette ligne entraîne une erreur du compilateur : `ShippingOrder so(42, 10.8);`.  Pour plus d’informations, consultez [des Conversions de types définis par l’utilisateur](../cpp/user-defined-type-conversions-cpp.md).  
  
##  <a name="default_constructors"></a>Constructeurs par défaut  
 *Constructeurs par défaut* n’avoir aucun paramètre ; ils suivent des règles légèrement différentes :  
  
 Les constructeurs par défaut sont un de la *fonctions membres spéciales*; si aucun constructeur n’est déclaré dans une classe, le compilateur fournit un constructeur par défaut :  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 Lorsque vous appelez un constructeur par défaut et que vous essayez d'utiliser des parenthèses, un avertissement s'affiche :  
  
```cpp  
class myclass{};  
int main(){  
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)  
}  
```  
  
 Voici un exemple de problème de type « Most Vexing Parse ». Puisque l'exemple d'expression peut être interprété comme la déclaration d'une fonction ou comme l'appel d'un constructeur par défaut, et puisque les analyseurs C++ privilégient les déclarations sur d'autres choses, l'expression est traitée comme une déclaration de fonction. Pour plus d’informations, consultez [Most Vexing Parse](http://en.wikipedia.org/wiki/Most_vexing_parse).  
  
 Si des constructeurs autres que ceux par défaut sont déclarés, le compilateur ne fournit pas de constructeur par défaut :  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
int main(){  
  
    Box box1(1, 2, 3);  
    Box box2{ 2, 3, 4 };  
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 Si une classe n'a aucun constructeur par défaut, un tableau d'objets de cette classe ne peut pas être construit seulement à l'aide de la syntaxe avec crochets. Par exemple, dans le bloc de code précédent, un tableau de Boxes ne peut pas être déclaré comme suit :  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 Toutefois, vous pouvez utiliser un ensemble de listes d'initialiseurs pour initialiser un tableau de Boxes :  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a>Copier et déplacer des constructeurs  
 A *constructeur de copie* est une fonction membre spéciale qui prend comme entrée une référence à un objet du même type et en fait une copie. Pour plus d’informations, consultez [constructeurs de copie et opérateurs d’assignation de copie (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md). A *constructeur de déplacement* est également une fonction membre spéciale qui déplace la propriété des données d’un objet existant à une nouvelle variable sans copier les données d’origine. Pour plus d’informations, consultez [constructeurs de déplacement et opérateurs d’assignation déplacer (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a>Constructeurs explicitement utilisés par défaut et supprimés  
 Vous pouvez explicitement *par défaut* constructeurs de copie, de constructeurs par défaut, de constructeurs de déplacement, de copier des opérateurs d’assignation, de déplacer des opérateurs d’assignation et les destructeurs. Vous pouvez explicitement *supprimer* toutes les fonctions membres spéciales. Pour plus d’informations, consultez [explicitement par défaut et supprimer des fonctions](../cpp/explicitly-defaulted-and-deleted-functions.md).  
  
##  <a name="constructors_in_derived_classes"></a>Constructeurs de Classes dérivées  
 Un constructeur de classe dérivée appelle toujours un constructeur de classe de base, afin de pouvoir s'appuyer sur des classes de base complètement construites avant d'effectuer tout travail supplémentaire. Les constructeurs de classe de base sont appelés par ordre de dérivation. Par exemple, si ClasseA est dérivée de ClasseB, qui est dérivée de ClasseC, le constructeur ClasseC est appelé en premier, puis le constructeur ClasseB, puis le constructeur ClasseA.  
  
 Si une classe de base n'a pas de constructeur par défaut, vous devez fournir les paramètres du constructeur de classe de base dans le constructeur de classe dérivée :  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height){  
       m_width = width;  
       m_length = length;  
       m_height = height;  
    }  
  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){  
        m_label = label;  
    }  
private:  
    string m_label;  
};  
  
int main(){  
  
    const string aLabel = "aLabel";  
    StorageBox sb(1, 2, 3, aLabel);  
}   
```  
  
### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Constructeurs pour les classes ayant un héritage multiple  
 Si une classe est dérivée de plusieurs classes de base, les constructeurs de classe de base sont appelés dans l'ordre dans lequel ils sont répertoriés dans la déclaration de la classe dérivée :  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 Vous devez obtenir la sortie suivante :  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a>Fonctions virtuelles dans les constructeurs  
 Nous vous recommandons d'être prudent lorsque vous appelez des fonctions virtuelles dans des constructeurs. Le constructeur de classe de base étant toujours appelé avant le constructeur de classe dérivée, la fonction qui est appelée dans le constructeur de base est la version de classe de base, et non la version de classe dérivée. Dans l'exemple suivant, la construction d'un objet `DerivedClass` provoque l'exécution de l'implémentation `BaseClass` de `print_it()` avant que le constructeur `DerivedClass` provoque l'exécution de l'implémentation `DerivedClass` de `print_it()` :  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass{  
public:  
    BaseClass(){  
        print_it();  
    }  
    virtual void print_it() {  
        cout << "BaseClass print_it" << endl;  
    }  
};  
  
class DerivedClass : public BaseClass {  
public:  
    DerivedClass() {  
        print_it();  
    }  
    virtual void print_it(){  
        cout << "Derived Class print_it" << endl;  
    }  
};  
  
int main() {  
  
    DerivedClass dc;  
}  
```  
  
 Voici la sortie :  
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a>Constructeurs et Classes composites  
 Les classes qui contiennent des membres de type de classe sont appelés *classes composites*. Lorsqu'un membre de type classe d'une classe composite est créé, le constructeur est appelé avant le propre constructeur de la classe. Lorsqu'une classe contenue n'a pas de constructeur par défaut, vous devez utiliser une liste d'initialisation dans le constructeur de la classe composite. Dans l'exemple `StorageBox` précédent, si vous remplacez le type de la variable membre `m_label` par une nouvelle classe `Label`, vous devez appeler le constructeur de classe de base et initialiser la variable `m_label` dans le constructeur `StorageBox` :  
  
```cpp  
class Label {  
public:  
    Label(const string& name, const string& address) { m_name = name; m_address = address; }  
    string m_name;  
    string m_address;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, Label label)   
        : Box(width, length, height), m_label(label){}  
private:  
    Label m_label;  
};  
  
int main(){  
// passing a named Label  
    Label label1{ "some_name", "some_address" };  
    StorageBox sb1(1, 2, 3, label1);  
  
    // passing a temporary label  
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });  
  
    // passing a temporary label as an initializer list  
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});  
}  
```  
  
##  <a name="delegating_constructors"></a>Constructeurs de délégation  
 A *délégation constructeur* appelle un autre constructeur de la même classe pour effectuer une partie du travail de l’initialisation. Dans l'exemple suivant, la classe dérivée a trois constructeurs : le second constructeur délègue au premier et le troisième constructeur délègue au second :  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 Voici la sortie :  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 L'objet créé par les constructeurs est entièrement initialisé dès qu'un constructeur est terminé. `DerivedContainer(int int1)` réussit, mais `DerivedContainer(int int1, int int2)` échoue et le destructeur est appelé.  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 Sortie :  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 Pour plus d’informations, consultez [d’initialisation uniforme et constructeurs de délégation](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
##  <a name="inheriting_constructors"></a>Constructeurs d’héritage (C ++ 11)  
 Une classe dérivée peut hériter des constructeurs d'une classe de base directe en utilisant une déclaration using, comme illustré dans l'exemple suivant :  
  
```  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:      
    Base() { cout << "Base()" << endl; }  
    Base(const Base& other) { cout << "Base(Base&)" << endl; }  
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }  
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }  
  
private:  
    int num;  
    char letter;  
};  
  
class Derived : Base  
{  
public:  
    // Inherit all constructors from Base  
    using Base::Base;  
  
private:  
    // Can't initialize newMember from Base constructors.  
    int newMember{ 0 };  
};  
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 L'instruction using place dans la portée tous les constructeurs de la classe de base, à l'exception de ceux qui ont une signature identique aux constructeurs de la classe dérivée. En général, il est préférable d'utiliser les constructeurs d'héritage quand la classe dérivée ne déclare aucun nouveau constructeur ni aucune nouvelle donnée membre.  
  
 Un modèle de classe peut hériter de tous les constructeurs d'un argument de type si ce type spécifie une classe de base :  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 Une classe dérivée ne peut pas hériter de plusieurs classes de base si ces classes de base possèdent des constructeurs qui ont une signature identique.  
  
##  <a name="rules_for_declaring_constructors"></a>Règles de déclaration des constructeurs  
 Un constructeur porte le même nom que sa classe. Un certain nombre de constructeurs peuvent être déclarés conformément aux règles des fonctions surchargées.  
  
 La `argument-declaration-list` peut être vide.  
  
 C++ définit deux genres particuliers de constructeurs, les constructeurs par défaut et les constructeurs de copie, décrits dans le tableau suivant.  
  
### <a name="default-and-copy-constructors"></a>Constructeurs par défaut et constructeurs de copie  
  
|Type de construction|Arguments|Objectif|  
|--------------------------|---------------|-------------|  
|Constructeur par défaut|Peut être appelé sans argument|Construire un objet par défaut du type de classe.|  
|Constructeur de copie|Peut accepter un argument unique de référence au même type de classe|Copier les objets du type de classe|  
  
 Les constructeurs par défaut peuvent être appelés sans argument. Toutefois, vous pouvez déclarer un constructeur avec une liste d'arguments si tous les arguments ont des valeurs par défaut. De même, les constructeurs de copie doivent accepter un argument unique de référence au même type de classe. Plus d'arguments peuvent être fournis si tous les arguments suivants ont des valeurs par défaut.  
  
 Si vous ne fournissez pas de constructeur, le compilateur tente de générer un constructeur par défaut. Si vous ne fournissez pas de constructeur de copie, le compilateur tente d'en générer un. Ces constructeurs générés par le compilateur sont considérés comme des fonctions membres publiques. Une erreur est générée si vous spécifiez un constructeur de copie avec un premier argument qui est un objet et non une référence.  
  
 Un constructeur par défaut généré par le compilateur installe l'objet (initialise des vftables et des vbtables, comme décrit précédemment), et il appelle les constructeurs par défaut pour les classes de base et les membres mais il n'effectue aucune autre action. Les constructeurs de classe de base et membres sont appelés uniquement s'ils existent, sont accessibles, et sont non équivoques.  
  
 Un constructeur de copie généré par le compilateur installe un nouvel objet et effectue une copie de membre du contenu de l'objet à copier. Si les constructeurs de classe de base ou membres existent, ils sont appelés. Sinon, une copie binaire est effectuée.  
  
 Si toutes les classes de base et membres d’une classe `type` ont des constructeurs de copie qui acceptent un **const** argument, le constructeur de copie générés par le compilateur accepte un argument unique de type **const** `type` **&**. Dans le cas contraire, le constructeur de copie générés par le compilateur accepte un argument unique de type `type` ** & **.  
  
 Vous pouvez utiliser un constructeur pour initialiser un **const** ou `volatile` objet, mais le constructeur lui-même ne peut pas être déclaré en tant que **const** ou `volatile`. La classe de stockage autorisée uniquement pour un constructeur est **inline**; utilisation de tout autre modificateur de classe de stockage, y compris le `__declspec` (mot clé), avec un constructeur entraîne une erreur du compilateur.  
  
 La convention d’appel stdcall est utilisée sur les fonctions membres statiques et les fonctions globales déclarées avec le **__stdcall** (mot clé) et qui n’utilisent pas d’une liste d’arguments variable. Lorsque vous utilisez la **__stdcall** mot clé dans une fonction membre non statique, telle qu’un constructeur, le compilateur utilise la convention d’appel thiscall. »  
  
 Les constructeurs de classes de base ne sont pas héritées par les classes dérivées. Lorsqu'un objet de type de classe dérivée est créé, il est construit en commençant par les composants de classe de base. Il passe ensuite aux composants de classe dérivée. Le compilateur utilise le constructeur de chaque classe de base comme partie de l’objet complet est initialisée (sauf en cas de dérivation virtuelle.  
  
##  <a name="explicitly_invoking_constructors"></a>Appel explicite des constructeurs  
 Les constructeurs peuvent être explicitement appelés dans un programme pour créer des objets d'un type donné. Par exemple, pour créer deux objets `Point` qui décrivent les extrémités d'une ligne, vous pouvez écrire le code suivant :  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 Deux objets de type `Point` sont créés, passés à la fonction `DrawLine`, puis détruits à la fin de l'expression (appel de fonction).  
  
 Une initialisation est un autre contexte dans lequel un constructeur est appelé explicitement :  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 Un objet de type `Point` est créé et initialisé à l'aide du constructeur qui accepte deux arguments de type `int`.  
  
 Les objets créés par l'appel explicite de constructeurs, comme dans les deux exemples précédents, sont sans nom et possèdent la durée de vie de l'expression dans laquelle ils sont créés. Ce sujet est abordé plus en détail dans [des objets temporaires](../cpp/temporary-objects.md).  
  
 En règle générale, il vaut mieux appeler une fonction membre à partir d'un constructeur car l'objet a été complètement configuré (les tables virtuelles ont été initialisées, etc.) avant l'exécution de la première ligne de code utilisateur. En revanche, l'appel d'une fonction membre virtuelle par une fonction membre pour une classe de base abstraite pendant la construction ou la destruction présente un risque potentiel.  
  
 Les constructeurs peuvent appeler des fonctions virtuelles. Lorsque les fonctions virtuelles sont appelées, la fonction appelée est celle définie pour la propre classe du constructeur (ou héritée de ses bases). L'exemple suivant illustre ce qui se produit lorsqu'une fonction virtuelle est appelée depuis un constructeur :  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 Lorsque le programme précédent est lancé, la déclaration `Derived d` provoque la séquence d'événements suivante :  
  
1.  Le constructeur de la classe `Derived` (`Derived::Derived`) est appelé.  
  
2.  Avant l'accès au corps du constructeur de la classe `Derived`, le constructeur de la classe `Base` (`Base::Base`) est appelé.  
  
 `Base::Base` appelle la fonction `f`, qui est une fonction virtuelle. Normalement, `Derived::f` est appelée car l'objet `d` est de type `Derived`. Étant donné que la fonction `Base::Base` est un constructeur, l'objet n'est pas encore de type `Derived`, et `Base::f` est appelée.  
  

