---
title: "Vue d&#39;ensemble des fonctions membres | Microsoft Docs"
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
  - "fonctions inline, traiter les fonctions membres en tant que"
  - "fonctions membres, définition dans une déclaration de classe"
  - "fonctions membres non statiques"
  - "ce pointeur, et fonctions membres non statiques"
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Vue d&#39;ensemble des fonctions membres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions membres sont statique ou non statique.  Le comportement des fonctions membres statique diffère d'autres fonctions membres car les fonctions membres statique n'ont aucun argument implicite **this**.  Les fonctions membres non statiques ont un pointeur **this**.  Les fonctions membres \(statique ou non statique\) peuvent être définies à l'intérieur ou à l'extérieur de la déclaration de classe.  
  
 Si une fonction membre est définie dans une déclaration de classe, elle est traitée comme une fonction inline, et il est inutile de qualifier le nom de fonction avec son nom de classe.  Bien que les fonctions définies dans les déclarations de classe aient déjà été traitées comme des fonctions inline, vous pouvez utiliser le mot clé **inline** pour documenter le code.  
  
 Un exemple de déclaration d'une fonction dans une déclaration de classe suit :  
  
```  
// overview_of_member_functions1.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit within the declaration  
    //  of class Account.  
    double Deposit( double HowMuch )  
    {  
        balance += HowMuch;  
        return balance;  
    }  
private:  
    double balance;  
};  
  
int main()  
{  
}  
```  
  
 Si une définition de fonction membre se trouve en dehors de la déclaration de classe, elle est traitée comme une fonction inline si elle est explicitement déclarée comme **inline**.  En outre, le nom de fonction dans la définition doit être qualifié avec son nom de classe par l'opérateur de résolution de portée \(`::`\).  
  
 L'exemple suivant est identique à la déclaration précédente de la classe `Account`, sauf que la fonction `Deposit` est définie à l'extérieur de la déclaration de classe :  
  
```  
// overview_of_member_functions2.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit but do not define it.  
    double Deposit( double HowMuch );  
private:  
    double balance;  
};  
  
inline double Account::Deposit( double HowMuch )  
{  
    balance += HowMuch;  
    return balance;  
}  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Bien que les fonctions membres puissent être définies dans une déclaration de classe ou séparément, aucune fonction membre ne peut être ajoutée à une classe après la classe définie.  
  
 Les classes contenant des fonctions membres peuvent avoir plusieurs déclarations, mais les fonctions membres elles\-mêmes doivent avoir une seule définition dans un programme.  Plusieurs définitions génèrent un message d'erreur au moment de la liaison.  Si une classe contient des définitions de fonction inline, les définitions de fonction doivent être identiques pour observer cette règle « d'une définition ».  
  
## Voir aussi  
 [Fonctions membres](../misc/member-functions-cpp.md)