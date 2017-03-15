---
title: "Assignation | Microsoft Docs"
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
  - "opérateurs d'assignation, surchargés"
  - "opérateurs (C++), d'assignation"
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assignation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'assignation \(**\=**\) est, à proprement parler, un opérateur binaire.  Sa déclaration est identique à celle de tout autre opérateur binaire, avec les exceptions suivantes :  
  
-   Il doit s'agir d'une fonction membre non statique.  Aucun `operator=` ne peut être déclaré comme fonction non\-membre.  
  
-   Il n'est pas hérité par les classes dérivées.  
  
-   Une fonction `operator=` par défaut peut être générée par le compilateur pour les types de classe si aucune n'existe. \(Pour plus d'informations sur les fonctions `operator=` par défaut, consultez [Assignation et initialisation membre à membre](http://msdn.microsoft.com/fr-fr/94048213-8b49-4416-8069-b1b7a6f271f9).\)  
  
 L'exemple suivant montre comment déclarer un opérateur d'assignation :  
  
```  
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 Notez que l'argument fourni est du côté droit de l'expression.  L'opérateur retourne l'objet pour conserver le comportement de l'opérateur d'assignation, qui retourne la valeur du côté gauche une fois l'assignation terminée.  Cela permet d'écrire des instructions telles que :  
  
```  
pt1 = pt2 = pt3;  
```  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)