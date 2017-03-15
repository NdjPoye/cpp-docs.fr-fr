---
title: "C4868 d’avertissement du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 26031e1ac6f39d745a772e1becf3f817213a59d8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4868"></a>C4868 d’avertissement du compilateur
compilateur de 'file(line_number)' ne peut pas appliquer ordre d’évaluation de gauche à droite dans la liste d’initialiseurs entre accolades  
  
 Les éléments d’une liste d’initialiseurs entre accolades doivent être évaluées dans l’ordre de gauche à droite. Il existe deux cas dans lesquels le compilateur est incapable de garantir cette commande : le premier est lorsque certains éléments sont des objets passés par valeur ; la seconde est lors de la compilation avec `/clr` et certains éléments sont les champs d’objets ou éléments de tableau. Lorsque le compilateur ne peut pas garantir l’évaluation de gauche à droite, il émet l’avertissement C4868.  
  
 Cet avertissement peut être généré en raison du travail de mise en conformité du compilateur pour Visual C++ 2015 Update 2. Le code compilé avant Visual C++ 2015 Update 2 génère désormais C4868.  
  
 Cet avertissement est désactivé par défaut. Utilisez `/Wall` pour activer cet avertissement.  
  
 Pour résoudre cet avertissement, envisagez d’abord si l’évaluation de gauche à droite des éléments de liste d’initialiseur est nécessaire, par exemple lorsque l’évaluation des éléments peut produire des effets dépend. Dans de nombreux cas, l’ordre dans lequel les éléments sont évalués n’a un effet observable.  
  
 Si l’ordre d’évaluation doit être de gauche à droite, considérez si il est possible de transmettre les éléments par référence (const) à la place. Une modification telle que cela supprime l’avertissement dans l’exemple de code suivant.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4868.  
  
```  
// C4868.cpp  
// compile with: /c /Wall  
#include <cstdio>  
  
class HasCopyConstructor  
{  
public:  
    int x;  
  
    HasCopyConstructor(int x): x(x) {}  
  
    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)  
    {  
        printf("Constructing %d\n", h.x);  
    }  
};  
  
class TripWarning4868  
{  
public:  
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.  
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}  
  
    // This variation will not trigger the warning:  
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}  
};  
  
int main()  
{  
    HasCopyConstructor a{1};  
    HasCopyConstructor b{2};  
  
    // the warning will indicate the below line, the usage of the braced initializer list.  
    TripWarning4868 warningOnThisLine{a, b};  
};  
```
