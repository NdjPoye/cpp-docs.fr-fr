---
title: "sizeof, op&#233;rateur | Microsoft Docs"
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
  - "sizeof_cpp"
  - "sizeof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sizeof (opérateur)"
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sizeof, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Donne la taille de son opérande par rapport à la taille du type `char`.  
  
> [!NOTE]
>  Pour plus d'informations sur l'opérateur `sizeof ...`, voir [Ellipses et modèles variadiques](../cpp/ellipses-and-variadic-templates.md).  
  
## Syntaxe  
  
```  
sizeof unary-expression sizeof  ( type-name )  
```  
  
## Notes  
 Le résultat de l'opérateur `sizeof` est de type `size_t`, un type intégral défini dans le fichier Include STDDEF.H.  Cet opérateur vous permet d'éviter de spécifier les tailles de données dépendantes de l'ordinateur dans vos programmes.  
  
 L'opérande de `sizeof` peut être l'un des opérandes suivants :  
  
-   Un nom de type.  Pour utiliser `sizeof` avec un nom de type, le nom doit être mis entre parenthèses.  
  
-   d'une expression.  Quand il est utilisé avec une expression, `sizeof` peut être spécifié avec ou sans parenthèses.  L'expression n'est pas évaluée.  
  
 Quand l'opérateur `sizeof` est appliqué à un objet de type `char`, il donne 1.  Quand l'opérateur `sizeof` est appliqué à un tableau, il donne le nombre total d'octets dans ce tableau, et non la taille du pointeur représenté par l'identificateur du tableau.  Pour obtenir la taille du pointeur représenté par l'identificateur du tableau, passez\-le en tant que paramètre à une fonction utilisant `sizeof`.  Par exemple :  
  
## Exemple  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## Résultat de l'exemple  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Quand l'opérateur `sizeof` est appliqué à un type `class`, `struct` ou `union`, le résultat est le nombre d'octets dans un objet de ce type, plus tout remplissage ajouté pour aligner les membres sur les limites de mots.  Le résultat ne correspond pas forcément à la taille calculée en additionnant les exigences en matière de stockage des membres individuels.  L'option de compilateur [\/Zp](../build/reference/zp-struct-member-alignment.md) et le pragma [pack](../preprocessor/pack.md) affectent les limites d'alignement des membres.  
  
 L'opérateur `sizeof` ne donne jamais 0, même pour une classe vide.  
  
 L'opérateur `sizeof` ne peut pas être utilisé avec les opérandes suivants :  
  
-   Fonctions.  \(Toutefois, `sizeof` peut être appliqué aux pointeurs vers des fonctions.\)  
  
-   Champ de bits.  
  
-   Classes indéfinies.  
  
-   Le type `void`.  
  
-   Tableaux alloués de manière dynamique.  
  
-   Tableaux externes.  
  
-   Types incomplets.  
  
-   Noms entre parenthèses de types incomplets.  
  
 Quand l'opérateur `sizeof` est appliqué à une référence, le résultat est le même que si `sizeof` est appliqué à l'objet lui\-même.  
  
 Si un tableau non dimensionné est le dernier élément d'une structure, l'opérateur `sizeof` retourne la taille de la structure sans le tableau.  
  
 L'opérateur `sizeof` est souvent utilisé pour calculer le nombre d'éléments dans un tableau à l'aide de l'expression de forme :  
  
```  
sizeof array / sizeof array[0]  
```  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)