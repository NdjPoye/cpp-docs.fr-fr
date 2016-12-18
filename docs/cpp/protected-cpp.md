---
title: "protected (C++) | Microsoft Docs"
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
  - "protected"
  - "protected_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "protected (mot clé) (C++)"
  - "protected (mot clé) (C++), accès aux membres"
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# protected (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## Notes  
 Le mot clé `protected` spécifie l'accès aux membres de classe de *member\-list* jusqu'au spécificateur d'accès suivant \(**public** ou `private`\) ou la fin de la définition de classe.  Les membres de classe déclarés comme `protected` peuvent être uniquement utilisés par ce qui suit :  
  
-   Les fonctions membres de la classe qui a initialement déclaré ces membres.  
  
-   Les friends de la classe qui a initialement déclaré ces membres.  
  
-   Les classes dérivées ayant un accès public ou protégé à partir de la classe qui a initialement déclaré ces membres.  
  
-   Les classes directes dérivées de manière privée qui ont également un accès privé aux membres protégés.  
  
 En faisant précéder le nom d'une classe de base, le mot clé `protected` indique que les membres publics et protégés de la classe de base sont des membres protégés de sa classe dérivée.  
  
 Les membres protégés ne sont pas aussi privés que les membres `private`, qui sont accessibles uniquement par les membres de la classe dans laquelle ils sont déclarés, mais ils ne sont pas aussi publics que les membres **public**, accessibles dans toute fonction.  
  
 Les membres protégés qui sont également déclarés comme **static** sont accessibles par tout friend ou fonction membre d'une classe dérivée.  Les membres protégés qui ne sont pas déclarés comme **statique** sont accessibles aux friends et aux fonctions membres dans une classe dérivée uniquement via un pointeur ou une référence vers la classe dérivée ou un objet de celle\-ci.  
  
 Pour obtenir des informations connexes, consultez [friend](../cpp/friend-cpp.md), [public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md) et le tableau d'accès aux membres dans [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md).  
  
## Spécifique \/clr  
 Dans les types CLR, les mots clés de spécificateur d'accès C\+\+ \(**public**, `private`, et `protected`\) peuvent affecter la visibilité des types et des méthodes quant aux assemblys.  Pour plus d'informations, consultez [Visibilité de type et de membre](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Les fichiers compilés avec [\/LN](../build/reference/ln-create-msil-module.md) ne sont pas affectés par ce comportement.  Dans ce cas, toutes les classes managées \(public ou privées\) seront visibles.  
  
## Spécifique END \/clr  
  
## Exemple  
  
```  
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## Voir aussi  
 [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)