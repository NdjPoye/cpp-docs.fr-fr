---
title: "Retours de fonction de type r&#233;f&#233;rence | Microsoft Docs"
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
  - "types de données (C++), types de retours de fonction"
  - "types de retours de fonction, type référence"
  - "fonctions (C++), types de retour"
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Retours de fonction de type r&#233;f&#233;rence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions peuvent être déclarées pour retourner un type référence.  Il existe deux raisons d'effectuer une déclaration :  
  
-   Les informations retournées sont un objet suffisamment grand pour que retourner une référence soit plus efficace que retourner une copie.  
  
-   Le type de la fonction doit être une l\-value.  
  
-   L'objet référencé ne sort pas de la portée lors du retour de la fonction.  
  
 Tout comme il peut être plus efficace de passer de grands objets *vers* les fonctions par référence, il peut également être plus efficace de retourner de grands objets *depuis* les fonctions par référence.  Le protocole de retour par référence élimine le besoin de copier l'objet dans un emplacement temporaire avant de le retourner.  
  
 Les types de retour par référence peuvent également être utiles lorsque la fonction doit prendre une l\-value.  La plupart des opérateurs surchargés appartiennent à cette catégorie, notamment l'opérateur d'assignation.  Les opérateurs surchargés sont décrits dans [Opérateurs surchargés](../cpp/operator-overloading.md).  
  
## Exemple  
 Prenons l'exemple de `Point` :  
  
```  
// refType_function_returns.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
class Point  
{  
public:  
// Define "accessor" functions as  
//  reference types.  
unsigned& x();  
unsigned& y();  
private:  
// Note that these are declared at class scope:  
unsigned obj_x;   
unsigned obj_y;   
};  
  
unsigned& Point :: x()  
{  
return obj_x;  
}  
unsigned& Point :: y()  
{  
return obj_y;  
}  
  
int main()  
{  
Point ThePoint;  
// Use x() and y() as l-values.  
ThePoint.x() = 7;  
ThePoint.y() = 9;  
  
// Use x() and y() as r-values.  
cout << "x = " << ThePoint.x() << "\n"  
<< "y = " << ThePoint.y() << "\n";  
}  
```  
  
## Sortie  
  
```  
x = 7  
y = 9  
```  
  
 Notez que les fonctions `x` et `y` sont déclarées comme retournant des types référence.  Ces fonctions peuvent être utilisées des deux côtés d'une instruction d'assignation.  
  
 Notez également que, dans main, l'objet Point reste dans la portée et ses membres de référence sont par conséquent toujours actifs et accessibles en toute sécurité.  
  
 Les déclarations des types référence doivent contenir des initialiseurs sauf dans les cas suivants :  
  
-   Déclaration `extern` explicite  
  
-   Déclaration d'une classe membre  
  
-   Déclaration sans classe  
  
-   Déclaration d'un argument d'une fonction ou du type de retour pour une fonction  
  
## Attention en retournant l'adresse d'une variable locale  
 Si vous déclarez un objet dans la portée locale, cet objet sera détruit lors du retour de la fonction.  Si la fonction retourne une référence à cet objet, cette référence est susceptible de provoquer une violation d'accès lors de l'exécution si l'appelant tente d'utiliser la référence null.  
  
```  
// C4172 means Don’t do this!!!  
Foo& GetFoo()  
{  
    Foo f;  
    ...  
    return f;  
} // f is destroyed here  
```  
  
 Le compilateur émet un avertissement dans ce cas : `avertissement C4172 : retourne l'adresse d'une variable locale ou temporaire`.  Dans des programmes simples, il est possible qu'occasionnellement aucune violation d'accès ne se produise si la référence est accessible par l'appelant avant le remplacement de l'emplacement de mémoire.  C'est le fruit du hasard.  Tenez compte de l'avertissement.  
  
## Voir aussi  
 [Références](../cpp/references-cpp.md)