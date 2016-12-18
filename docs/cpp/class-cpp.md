---
title: "class (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "class_cpp"
  - "class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class (mot clé C++)"
  - "types de classes, instructions class"
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# class (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `class` déclare un type de classe ou définit un objet d'un type de classe.  
  
## Syntaxe  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### Paramètres  
 `template-spec`  
 Spécifications de modèle facultatives.  Pour plus d'informations, consultez [Spécifications de modèle](../Topic/Template%20Specifications.md).  
  
 `class`  
 Le mot clé `class`.  
  
 `ms-decl-spec`  
 Spécification de classe de stockage facultative.  Pour plus d'informations, consultez le mot clé [\_\_declspec](../cpp/declspec.md).  
  
 `tag`  
 Le nom de type donné à la classe.  La balise devient un mot réservé dans la portée de la classe.  La balise est facultative.  Si elle est omise, une classe anonyme est définie.  Pour plus d'informations, consultez [Types de classes anonymes](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Liste facultative des classes ou structures dont dérivent les membres de cette classe.  Consultez [Classes de base](../cpp/base-classes.md) pour plus d'informations.  Chaque nom de classe de base ou de structure peut être précédé d'un spécificateur d'accès \([public](../cpp/public-cpp.md), [privé](../cpp/private-cpp.md) ou [protégé](../cpp/protected-cpp.md)\) et du mot clé [virtuel](../cpp/virtual-cpp.md).  Consultez le tableau d'accès aux membres dans [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md), pour plus d'informations.  
  
 `member-list`  
 Liste des membres de la classe.  Pour plus d'informations, consultez [Vue d'ensemble des membres de classe](../cpp/class-member-overview.md).  
  
 `declarators`  
 Liste des déclarateurs spécifiant les noms d'une ou plusieurs instances du type de la classe.  Les déclarateurs peuvent inclure des listes d'initialiseurs si toutes les données membres de la classe sont `public`.  Ceci est plus courant dans les structures, dont les données membres sont par défaut `public`, que dans les classes.  Consultez [Vue d'ensemble des déclarateurs](../cpp/overview-of-declarators.md) pour plus d'informations.  
  
## Notes  
 Pour plus d'informations sur les classes en général, consultez l'une des rubriques suivantes :  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [\_\_multiple\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_single\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_virtual\_inheritance](../cpp/inheritance-keywords.md)  
  
 Pour plus d'informations sur les classes et les structures managées, consultez [Classes et structures](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Exemple  
  
```  
// class.cpp  
// compile with: /EHsc  
// Example of the class keyword  
// Exhibits polymorphism/virtual functions.  
  
#include <iostream>  
#include <string>  
#define TRUE = 1  
using namespace std;  
  
class dog  
{  
public:  
   dog()  
   {  
      _legs = 4;  
      _bark = true;  
   }  
  
   void setDogSize(string dogSize)  
   {  
      _dogSize = dogSize;  
   }  
   virtual void setEars(string type)      // virtual function  
   {  
      _earType = type;  
   }  
  
private:  
   string _dogSize, _earType;  
   int _legs;  
   bool _bark;  
  
};  
  
class breed : public dog  
{  
public:  
   breed( string color, string size)  
   {  
      _color = color;  
      setDogSize(size);  
   }  
  
   string getColor()  
   {  
      return _color;  
   }  
  
   // virtual function redefined  
   void setEars(string length, string type)  
   {  
      _earLength = length;  
      _earType = type;  
   }  
  
protected:  
   string _color, _earLength, _earType;  
};  
  
int main()  
{  
   dog mongrel;  
   breed labrador("yellow", "large");  
   mongrel.setEars("pointy");  
   labrador.setEars("long", "floppy");  
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;  
}  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Classes et structs](../cpp/classes-and-structs-cpp.md)