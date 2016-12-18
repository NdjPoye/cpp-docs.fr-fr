---
title: "Classes abstraites (C++) | Microsoft Docs"
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
  - "classes abstraites"
  - "classes de base, classes abstraites"
  - "classes (C++), abstract"
  - "classes dérivées, classes abstraites"
ms.assetid: f0c5975b-39de-4d68-9640-6ce57f4632e6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes abstraites (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes abstraites agissent comme des expressions de concepts généraux dont des classes plus spécifiques peuvent être dérivées.  Vous ne pouvez pas créer un objet d'un type de classe abstraite ; en revanche, vous pouvez utiliser des pointeurs et des références à des types de classe abstraite.  
  
 Une classe contenant au moins une fonction virtuelle pure est considérée comme une classe abstraite.  Les classes dérivées de la classe abstraite doivent implémenter la fonction virtuelle pure, sinon elles aussi sont des classes abstraites.  
  
 Une fonction virtuelle est déclarée comme « pure » à l'aide de la syntaxe *pure\-specifier* \(décrite dans [Implémentation de protocole de classe](http://msdn.microsoft.com/fr-fr/a319f1b3-05e8-400e-950a-1ca6eb105ab5)\).  Prenons l'exemple présenté dans [Fonctions virtuelles](../cpp/virtual-functions.md).  L'objectif de la classe `Account` est de fournir une fonctionnalité générale, mais les objets de type `Account` sont trop généraux pour être utiles.  Par conséquent, `Account` est un bon candidat pour une classe abstraite :  
  
```  
// deriv_AbstractClasses.cpp  
// compile with: /LD  
class Account {  
public:  
   Account( double d );   // Constructor.  
   virtual double GetBalance();   // Obtain balance.  
   virtual void PrintBalance() = 0;   // Pure virtual function.  
private:  
    double _balance;  
};  
  
```  
  
 La seule différence entre cette déclaration et la précédente vient du fait que `PrintBalance` est déclaré avec le spécificateur pure \(`= 0`\).  
  
## Restrictions sur les classes abstraites  
 Les classes abstraites ne peuvent pas être utilisées pour :  
  
-   Variables ou données membres  
  
-   Types d'arguments  
  
-   Types de retour de fonction  
  
-   Types de conversions explicites  
  
 Une autre restriction est que si le constructeur d'une classe abstraite appelle une fonction virtuelle pure directement ou indirectement, le résultat est indéfini.  Toutefois, les constructeurs et les destructeurs des classes abstraites peuvent appeler d'autres fonctions membres.  
  
 Les fonctions virtuelles pures peuvent être définies pour les classes abstraites, mais elles peuvent être appelées directement en utilisant la syntaxe suivante :  
  
 *abstract\-class\-name* `::` *function\-name***\( \)**  
  
 C'est utile lors de la création des hiérarchies de classes dont les classes de base incluent des destructeurs virtuels purs, car les destructeurs de classe de base sont toujours appelés dans le processus de destruction d'un objet.  Prenons l'exemple suivant :  
  
```  
// Declare an abstract base class with a pure virtual destructor.  
// deriv_RestrictionsonUsingAbstractClasses.cpp  
class base {  
public:  
    base() {}  
    virtual ~base()=0;  
};  
  
// Provide a definition for destructor.  
base::~base() {}  
  
class derived:public base {  
public:  
    derived() {}  
    ~derived(){}  
};  
  
int main() {  
    derived *pDerived = new derived;  
    delete pDerived;  
}  
```  
  
 Lorsque l'objet pointé par `pDerived` est supprimé, le destructeur de la classe `derived` est appelé puis le destructeur de la classe `base`.  L'implémentation vide de la fonction virtuelle pure garantit qu'au moins une implémentation existe pour la fonction.  
  
> [!NOTE]
>  Dans l'exemple précédent, la fonction virtuelle pure `base::~base` est appelée implicitement depuis `derived::~derived`.  Il est également possible d'appeler des fonctions virtuelles pures explicitement en utilisant un nom de fonction membre qualifié complet.  
  
## Voir aussi  
 [Héritage](../cpp/inheritance-cpp.md)