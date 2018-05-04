---
title: Affectation | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66fd08215c3849bf487578b28b1824afbec14c52
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="assignment"></a>Attribution
L’opérateur d’assignation (**=**) est en principe, un opérateur binaire. Sa déclaration est identique à celle de tout autre opérateur binaire, avec les exceptions suivantes :  
  
-   Il doit s'agir d'une fonction membre non statique. Aucun `operator=` ne peut être déclaré comme fonction non-membre.  
  
-   Il n'est pas hérité par les classes dérivées.  
  
-   Une fonction `operator=` par défaut peut être générée par le compilateur pour les types de classe si aucune n'existe. (Pour plus d’informations sur la valeur par défaut `operator=` fonctions, consultez [assignation et initialisation](http://msdn.microsoft.com/en-us/94048213-8b49-4416-8069-b1b7a6f271f9).)  
  
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
  
 Notez que l'argument fourni est du côté droit de l'expression. L'opérateur retourne l'objet pour conserver le comportement de l'opérateur d'assignation, qui retourne la valeur du côté gauche une fois l'assignation terminée. Cela permet d'écrire des instructions telles que :  
  
```  
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)