---
title: "STL/CLR, conteneurs | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conteneurs, STL/CLR"
  - "STL/CLR, conteneurs"
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# STL/CLR, conteneurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque de STL\/CLR a les mêmes conteneurs que ceux de la bibliothèque C\+\+ standard, mais elle fonctionne dans un environnement managé du .NET Framework.  Si vous êtes familiarisé avec la Standard Template Library \(STL\), STL\/CLR est la meilleure façon de continuer à utiliser les compétences que vous avez déjà étendues lors de la mise à niveau de votre code pour cibler le common langage runtime \(CLR\).  
  
 Ce document fournit une vue d'ensemble des conteneurs dans STL\/CLR, tels que les conditions requises pour les éléments conteneurs, les types d'éléments que vous pouvez insérer dans des conteneurs, et les problèmes de propriété avec les éléments des conteneurs.  Le cas échéant, les différences entre la Standard Template Library native et le STL\/CLR sont indiquées.  
  
## Spécifications pour les éléments de conteneurs  
 Tous les éléments insérés dans des conteneurs STL doivent obéir à certaines instructions.  Pour plus d'informations, consultez [Spécifications pour les éléments de conteneur STL\/CLR](../dotnet/requirements-for-stl-clr-container-elements.md).  
  
## Éléments de conteneurs valides  
 Les conteneurs STL\/CLR peuvent contenir l'un des deux types d'éléments :  
  
-   Handle vers des types référence.  
  
-   Types référence.  
  
-   Types de valeurs non encapsulés.  
  
 Vous ne pouvez pas insérer les valeurs de type encapsulé dans les conteneurs STL\/CLR.  
  
### Handle vers des types référence.  
 Vous pouvez insérer un handle à un type référence dans un conteneur STL\/CLR.  Un descripteur en C\+\+ qui cible le CLR est analogue à un pointeur en mode natif C\+\+.  Pour plus d'informations, consultez [Handle sur l'opérateur Object \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### Exemple  
 L'exemple suivant montre comment insérer un descripteur sur un objet Employee dans [cliext::set](../dotnet/set-stl-clr.md).  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee^ empl1419 = gcnew Employee();  
    empl1419->Name = L"Darin Lockert";  
    empl1419->EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee^>^ emplSet = gcnew set<Employee^>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### Types référence  
 Il est également possible d'insérer un type référence \(plutôt qu'un handle à un type de référence\) dans un conteneur STL\/CLR.  La principale différence est ici que lorsqu'un conteneur de types référence est supprimé, le destructeur est appelé pour tous les éléments du conteneur.  Dans un conteneur de handles vers des types référence, les destructeurs de ces éléments ne seraient pas appelés.  
  
#### Exemple  
 L'exemple suivant indique comment insérer un objet Employee dans un `cliext::set`.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
    ~Employee() { }  
  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee^ empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl->EmployeeNumber, empl->Name);  
    }  
  
    return 0;  
}  
```  
  
### Types de valeurs non encapsulés.  
 Vous pouvez également insérer un type de valeur non encapsulé dans un conteneur STL\/CLR.  Un type de valeur non encapsulé est un type de valeur qui n'a pas été *encapsulé* dans un type de référence.  
  
 Un élément de type valeur peut être l'un des types de valeurs standard, comme `int`, ou il peut s'agir d'un type défini par l'utilisateur, tel que `value class`.  Pour plus d’informations, consultez [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### Exemple  
 L'exemple suivant modifie le premier exemple en transformant la classe Employee en un type de valeur.  Ce type de valeur est alors inséré dans `cliext::set` comme dans le premier exemple.  
  
```  
// cliext_container_valid_valuetype.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
value class Employee  
{  
public:  
    // Associative containers such as maps and sets  
    // require a comparison operator to be defined  
    // to determine proper ordering.  
    bool operator<(const Employee^ rhs)  
    {  
        return (employeeNumber < rhs->employeeNumber);  
    }  
  
    // The employee's name.  
    property String^ Name  
    {  
        String^ get() { return name; }  
        void set(String^ value) { name = value; }  
    }  
  
    // The employee's employee number.  
    property int EmployeeNumber  
    {  
        int get() { return employeeNumber; }  
        void set(int value) { employeeNumber = value; }  
    }  
  
private:  
    String^ name;  
    int employeeNumber;  
};  
  
int main()  
{  
    // Create a new employee object.  
    Employee empl1419;  
    empl1419.Name = L"Darin Lockert";  
    empl1419.EmployeeNumber = 1419;  
  
    // Add the employee to the set of all employees.  
    set<Employee>^ emplSet = gcnew set<Employee>();  
    emplSet->insert(empl1419);  
  
    // List all employees of the company.  
    for each (Employee empl in emplSet)  
    {  
        Console::WriteLine("Employee Number {0}: {1}",  
            empl.EmployeeNumber, empl.Name);  
    }  
  
    return 0;  
}  
```  
  
 Si vous tentez d'insérer un handle à un type de valeur dans un conteneur, [Erreur du compilateur C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) est généré.  
  
### Conséquences de performances et de mémoire  
 Vous devez considérer plusieurs facteurs pour déterminer s'il faut utiliser des handles vers des types référence ou des types de valeurs en tant qu'éléments de conteneur.  Si vous décidez d'utiliser des types de valeur, n'oubliez pas qu'une copie de l'élément est effectuée chaque fois qu'un élément est inséré dans le conteneur.  Pour les petits objets, ce ne doit pas être un problème , mais si les objets à insérer sont volumineux, les performances peuvent en pâtir.  De plus, si vous utilisez des types de valeurs, il est impossible d'inscrire un élément dans plusieurs conteneurs en même temps puisque chaque conteneur aurait sa propre copie de l'élément.  
  
 Si vous décidez d'utiliser des handles vers des types référence à la place, les performances peuvent s'améliorer car il n'est pas nécessaire d'effectuer une copie de l'élément lorsqu'il est inséré dans le conteneur.  En outre, contrairement à des types de valeur, le même élément peut exister dans plusieurs conteneurs.  Toutefois, si vous décidez d'utiliser les handles, vous devez veiller à vérifier que le handle est valide et que l'objet auquel il se rapporte n'a pas été supprimé ailleurs dans le programme.  
  
## Problèmes de propriété avec les conteneurs  
 Les conteneurs en STL\/CLR travaillent sur la sémantique de la valeur.  Chaque fois que vous insérez un élément dans un conteneur, une copie de cet élément est insérée.  Si vous souhaitez obtenir la sémantique comme référence, vous pouvez insérer un descripteur sur un objet au lieu de l'objet lui\-même.  
  
 Lorsque vous appelez une méthode clear ou erase d'un conteneur de handles d'objets, les objets qui sont référencés ne sont pas libérés de la mémoire.  Vous devez soit explicitement supprimer l'objet, ou, puisque ces objets résident sur le tas managé, activer le garbage collector pour libérer de la mémoire une fois qu'il a déterminé si l'objet n'est plus utilisé.  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)