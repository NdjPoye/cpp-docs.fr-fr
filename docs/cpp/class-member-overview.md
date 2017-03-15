---
title: "Vue d&#39;ensemble des membres de classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membres de classe"
  - "membres de classe, types de"
  - "membres"
  - "membres, types de membres de classe"
ms.assetid: 8802cfa9-705d-4f37-acde-245d6838010c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Vue d&#39;ensemble des membres de classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe ou un struct se compose de ses membres.  Le travail exécuté par une classe est effectué par ses fonctions membres.  L'état géré est stocké dans ses données membres.  L'initialisation des membres est effectuée par les constructeurs tout comme le travail de nettoyage, tel que la libération de mémoire et de ressources.  En C\+\+11 et versions ultérieures, les données membres peuvent \(et généralement doivent\) être initialisées au point de déclaration.  
  
## Genres de membres de classe  
 La liste complète des catégories de membres est la suivante :  
  
-   Fonctions membres spéciales.  
  
-   [Fonctions membres](../misc/member-functions-cpp.md).  
  
-   [Données membres](../cpp/static-members-cpp.md), notamment les types intégrés et autres types définis par l'utilisateur.  
  
-   Opérateurs  
  
-   [Déclarations de classes imbriquées](../cpp/nested-class-declarations.md) et  
  
-   [Unions](../cpp/unions.md)  
  
-   [Énumérations](../cpp/enumerations-cpp.md).  
  
-   [Champ de bits](../cpp/cpp-bit-fields.md).  
  
-   [Friends](../cpp/friend-cpp.md).  
  
-   [Alias et typedefs](../cpp/aliases-and-typedefs-cpp.md).  
  
    > [!NOTE]
    >  Les friends sont inclus dans la liste précédente parce qu'ils figurent dans la déclaration de classe.  Toutefois, ils ne sont pas des membres de classe True, car ils ne sont pas dans la portée de la classe.  
  
## Exemple de déclaration de classe  
 L'exemple suivant illustre une déclaration de classe simple :  
  
```  
// TestRun.h  
  
class TestRun  
{  
    // Start member list.  
  
    //The class interface accessible to all callers.  
public:  
    // Use compiler-generated default constructor:  
    TestRun() = default;   
    // Don't generate a copy constructor:  
    TestRun(const TestRun&) = delete;    
    TestRun(std::string name);  
    void DoSomething();  
    int Calculate(int a, double d);  
    virtual ~TestRun();  
    enum class State { Active, Suspended };  
  
    // Accessible to this class and derived classes only.  
protected:  
    virtual void Initialize();  
    virtual void Suspend();  
    State GetState();  
  
    // Accessible to this class only.  
private:  
    // Default brace-initialization of instance members:  
    State _state{ State::Suspended };   
    std::string _testName{ "" };   
    int _index{ 0 };  
  
    // Non-const static member:  
    static int _instances;  
    // End member list.  
};  
  
// Define and initialize static member.  
int TestRun::_instances{ 0 };  
```  
  
## Accessibilité des membres  
 Les membres d'une classe sont déclarés dans la liste des membres.  La liste des membres d'une classe peut être divisée en un nombre quelconque de sections `private`, `protected` et **public** avec les mots clés appelés spécificateurs d'accès.  Un signe deux\-points **:** doit suivre le spécificateur d'accès.  Ces sections n'ont pas besoin d'être contiguës, autrement aucun de ces mots clés ne peut apparaître plusieurs fois dans la liste des membres.  Le mot clé désigne l'accès de tous les membres jusqu'au spécificateur d'accès suivant ou l'accolade fermante.  Pour plus d'informations, consultez [Contrôle d'accès aux membres \(C\+\+\)](../cpp/member-access-control-cpp.md).  
  
## Membres static  
 Des données membres peuvent être déclarées comme statiques, ce qui signifie que tous les objets de la classe ont accès à la même copie de celles\-ci.  Une fonction membre peut être déclarée comme statique, auquel cas elle peut accéder uniquement aux données membres statiques de la classe \(et n'a aucun pointeur *this*\).  Pour plus d'informations, consultez [Données membres statiques](../cpp/static-members-cpp.md).  
  
## Fonctions membres spéciales  
 Les fonctions membres spéciales sont des fonctions qui sont fournies automatiquement par le compilateur si vous ne les spécifiez pas dans votre code source.  
  
1.  Constructeur par défaut  
  
2.  Constructeur de copie  
  
3.  Constructeur de déplacement **\(C\+\+11\)**  
  
4.  Opérateur d'assignation de copie  
  
5.  Opérateur d'assignation de déplacement **\(C\+\+11\)**  
  
6.  Destructeur  
  
## Initialisation de membre à membre  
 En C\+\+11 et versions ultérieures, les déclarateurs de membres non statiques peuvent contenir des initialiseurs.  
  
```  
  
class CanInit  
{  
public:  
    long num {7};       // OK in C++11  
    int k = 9;          // OK in C++11  
    static int i = 9; // Error: must be defined and initialized  
                      // outside of class declaration.  
  
    // initializes num to 7 and k to 9  
    CanInit(){}  
  
    // overwrites original initialized value of num:  
    CanInit(int val) : num(val) {}  
};  
int main()  
{  
}  
```  
  
 Si une valeur est assignée à un membre dans un constructeur, cette valeur remplace celle avec laquelle le membre a été initialisé au point de déclaration.  
  
 Il n'existe qu'une seule copie partagée des données membres statiques pour tous les objets d'un type de classe donné.  Les membres de données statiques doivent être définies et peuvent être initialisées au niveau de la portée du fichier.  \(Pour plus d'informations sur les membres de données statiques, consultez [Membres de données statiques](../cpp/static-members-cpp.md).\) L'exemple suivant montre comment effectuer ces initialisations :  
  
```  
// class_members2.cpp  
class CanInit2  
{  
public:  
    CanInit2() {} // Initializes num to 7 when new objects of type   
                 //  CanInit are created.  
    long     num {7};  
    static int i;  
    static int j;  
};  
  
// At file scope:  
  
// i is defined at file scope and initialized to 15.  
// The initializer is evaluated in the scope of CanInit.  
int CanInit2::i = 15;  
  
// The right side of the initializer is in the scope   
// of the object being initialized  
int CanInit2::j = i;  
```  
  
> [!NOTE]
>  Le nom de classe, `CanInit2`, doit précéder `i` pour spécifier que le `i` défini est un membre de classe `CanInit2`.  
  
## Voir aussi  
 [Classes et structs](../cpp/classes-and-structs-cpp.md)