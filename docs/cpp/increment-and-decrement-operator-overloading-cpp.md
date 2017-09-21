---
title: "Surcharge d&#39;op&#233;rateurs d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation (C++) | Microsoft Docs"
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
  - "opérateurs de décrémentation"
  - "opérateurs de décrémentation, types de"
  - "opérateur d'incrémentation"
  - "opérateur d'incrémentation, types de"
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Surcharge d&#39;op&#233;rateurs d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs d'incrémentation et de décrémentation appartiennent à une catégorie spéciale car chacun comporte deux variantes :  
  
-   Incrémentation préfixée et incrémentation suffixée  
  
-   Décrémentation préfixée et décrémentation suffixée  
  
 Lorsque vous écrivez des fonctions d'opérateur surchargées, il peut être utile d'implémenter des versions distinctes des versions préfixées et suffixées de ces opérateurs.  Pour distinguer les deux, la règle suivante est observée : la forme préfixée de l'opérateur est déclarée exactement de la même manière que tout autre opérateur unaire. La forme suffixée accepte un argument supplémentaire de type `int`.  
  
> [!NOTE]
>  Pour spécifier un opérateur surchargé pour la forme suffixée de l'opérateur d'incrémentation ou de décrémentation, l'argument supplémentaire doit être de type `int`. La spécification de tout autre type génère une erreur.  
  
 L'exemple suivant indique comment définir les opérateurs d'incrémentation et de décrémentation préfixés et suffixés pour la classe `Point` :  
  
```  
// increment_and_decrement1.cpp  
class Point  
{  
public:  
   // Declare prefix and postfix increment operators.  
   Point& operator++();       // Prefix increment operator.  
   Point operator++(int);     // Postfix increment operator.  
  
   // Declare prefix and postfix decrement operators.  
   Point& operator--();       // Prefix decrement operator.  
   Point operator--(int);     // Postfix decrement operator.  
  
   // Define default constructor.  
   Point() { _x = _y = 0; }  
  
   // Define accessor functions.  
   int x() { return _x; }  
   int y() { return _y; }  
private:  
   int _x, _y;  
};  
  
// Define prefix increment operator.  
Point& Point::operator++()  
{  
   _x++;  
   _y++;  
   return *this;  
}  
  
// Define postfix increment operator.  
Point Point::operator++(int)  
{  
   Point temp = *this;  
   ++*this;  
   return temp;  
}  
  
// Define prefix decrement operator.  
Point& Point::operator--()  
{  
   _x--;  
   _y--;  
   return *this;  
}  
  
// Define postfix decrement operator.  
Point Point::operator--(int)  
{  
   Point temp = *this;  
   --*this;  
   return temp;  
}  
int main()  
{  
}  
```  
  
 Les mêmes opérateurs peuvent être définis dans la portée de fichier \(globalement\) à l'aide des en\-têtes de fonction suivants :  
  
```  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 L'argument de type `int` qui désigne la forme suffixée de l'opérateur d'incrémentation ou de décrémentation n'est pas couramment utilisé pour passer des arguments.  Il contient généralement la valeur 0.  Toutefois, il peut être utilisé comme suit :  
  
```  
// increment_and_decrement2.cpp  
class Int  
{  
public:  
    Int &operator++( int n );  
private:  
    int _i;  
};  
  
Int& Int::operator++( int n )  
{  
    if( n != 0 )    // Handle case where an argument is passed.  
        _i += n;  
    else  
        _i++;       // Handle case where no argument is passed.  
    return *this;  
}  
int main()  
{  
   Int i;  
   i.operator++( 25 ); // Increment by 25.  
}  
```  
  
 Il n'existe aucune autre syntaxe pour utiliser les opérateurs d'incrémentation ou de décrémentation pour passer ces valeurs que l'appel explicite, comme indiqué dans le code précédent.  Une méthode plus simple pour implémenter cette fonctionnalité consiste à surcharger l'opérateur d'ajout\/d'assignation \(`+=`\).  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)