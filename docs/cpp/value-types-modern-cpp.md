---
title: "Types de valeur (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types de valeur (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes C\+\+ sont par défaut des types de valeur.  Cette rubrique fournit une vue d'ensemble préliminaire des types de valeurs et les problèmes concernant leur utilisation.  
  
## Par valeur ou par référence  
 Comme indiqué précédemment, les classes C\+\+ sont par défaut des types de valeur.  Mais vous pouvez les spécifier comme types référence pour activer le comportement polymorphe qui prend en charge la programmation orientée objet.  Les types de valeurs sont parfois rendus ne la différencie du contrôle de mémoire et de mise en page, tandis que les types référence sont sur les classes de base et des fonctions virtuelles à des fins polymorphes.  Par défaut, les types valeur sont copiables. Ils ont chacun un constructeur de copie et un opérateur d'assignation de copie.  Lorsque vous spécifiez un type référence, rendez la classe impossible à copier \(désactivez le constructeur de copie et copiez l'opérateur d'affectation\) et utilisez un destructeur virtuel, ce qui assure la prise en charge du polymorphisme.  Les types valeur concernent également le contenu qui, en cas de copie, vous donne deux valeurs distinctes que vous pouvez modifier séparément.  Les types référence sont des informations d'identité – qu'un peu l'objet est \-il ?  Pour cette raison, « types de référence » est également sous le nom « types polymorphes ».  
  
 Si vous voulez vraiment un type comme référence \(classe de base, fonctions virtuelles\), vous devez désactiver explicitement la sauvegarde, comme indiqué dans la classe d'`MyRefType` dans le code suivant.  
  
```cpp  
  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 Compilation du code ci\-dessus génère l'erreur suivante :  
  
  **test.cpp \(15\) : erreur C2248 : « MyRefType::operator \= » : ne peut pas accéder au membre privée déclaré dans MyRefType des classes »**  
 **meow.cpp \(5\) : consultez la déclaration « MyRefType::operator \= »**  
 **meow.cpp \(3\) : consultez la déclaration «  » MyRefType**   
## Types de valeurs et efficacité de déplacement  
 La surcharge d'allocation de sauvegarde est évitée en raison de les optimisations de copie.  Par exemple, lorsque vous insérez une chaîne au milieu d'un vecteur de chaînes, il n'y a aucune surcharge de redistribution de sauvegarde, qu'un déplacement même s'il en résulte un développement du vecteur lui\-même.  Cela s'applique aussi aux autres opérations, par exemple effectuant une opération d'ajout sur deux objets de grande taille.  Comment activez\-vous ces optimisations d'opération de valeur ?  Dans certains compilateurs C\+\+, le compilateur il vérifie automatiquement implicitement, comme les constructeurs d'envoi peut être généré automatiquement par le compilateur.  Toutefois, dans Visual C\+\+, votre classe a besoin de exécution «  » pour déplacer l'attribution les constructeurs et en indiquant dans la définition de classe.  Cela s'effectue en utilisant la double référence de rvalue et commercial \(&&\) dans les déclarations et la définition d'une fonction membre appropriées des méthodes de constructeur de déplacement et d'assignation de déplacement.  Vous devez également insérer code correct « volez les entrailles » hors de l'objet source.  
  
 Comment décidez\-vous si vous avez besoin de déplacement activé ?  Si vous savez déjà vous avez besoin de la construction de copie activée, vous souhaitez peut\-être déplacer activé s'il est préférable d'une copie complète.  Toutefois, si vous savez vous avez besoin de prise en charge de déplacer, cela ne signifie pas nécessairement que la copie activée.  Ce dernier cas est appelé « type réservé à déplacer.  Un exemple déjà dans la bibliothèque standard est `unique_ptr`.  Une note marginal, `auto_ptr` ancien est déconseillé, et a été remplacé par `unique_ptr` précisément en raison de l'absence de prise en charge de la sémantique de déplacement dans la version précédente C\+\+.  
  
 En utilisant la sémantique de déplacement vous pouvez RETURN\-par\- unique ou INSERT\-dans\- moyen.  Le déplacement est une optimisation de copie.  Il y a besoin d'allocation des segments pour contourner ce problème.  Examinons le code ci\-dessous.  
  
```cpp  
  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### Activer le déplacement des types de valeurs appropriées  
 Pour une classe en tant que valeur où le déplacement peut être préférable d'une copie complète, activer la construction de déplacement et l'attribution de déplacement pour l'efficacité.  Examinons le code ci\-dessous.  
  
```cpp  
  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 Si vous activez la construction et l'affectation de copie, activez également la construction et l'affectation du déplacement s'il est préférable d'une copie complète.  
  
 Certains types *non multiples* sont réservés à déplacer, comme lorsque vous ne pouvez pas dupliquer une ressource, seule la propriété de transfert.  Par exemple : `unique_ptr`  
  
## Section  
 Contenu  
  
## Voir aussi  
 [Système de type C\+\+](../cpp/cpp-type-system-modern-cpp.md)   
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)