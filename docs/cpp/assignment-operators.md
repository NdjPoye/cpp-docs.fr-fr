---
title: "Opérateurs d’assignation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '>>='
- xor_eq
- '&='
- <<=
- -=
- and_eq
- ^=
- '|='
- /=
- '%='
- or_eq
- +=
- '*='
dev_langs:
- C++
helpviewer_keywords:
- or_eq operator
- '&= operator'
- operators [C++], assignment
- assignment operators [C++], C++
- xor_eq operator
- += operator
- and_eq operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- assignment operators [C++]
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 34ed921ed7eb690372f1635ed845271fa7520a86
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="assignment-operators"></a>Opérateurs d'assignation
## <a name="syntax"></a>Syntaxe  
  
```  
  
      expression assignment-operator expression   
assignment-operator : one of  
   =   *=   /=   %=   +=   -=   <<=   >>=   &=   ^=   |=  
```  
  
## <a name="remarks"></a>Remarques  
 Les opérateurs d’assignation stockent une valeur dans l’objet indiqué par l’opérande de gauche. Il existe deux types d'opérations d'assignation : l'assignation simple, dans laquelle la valeur du deuxième opérande est stockée dans l'objet spécifié par le premier opérande, et l'assignation composée, dans laquelle une opération arithmétique, de décalage ou de bits est effectuée avant d'enregistrer le résultat. Tous les opérateurs d'assignation décrits dans le tableau suivant, à l'exception de l'opérateur =, sont des opérateurs d'assignation composée.  
  
### <a name="assignment-operators"></a>Opérateurs d'assignation  
  
|Opérateur|Signification|  
|--------------|-------------|  
|**=**|Enregistre la valeur du deuxième opérande dans l’objet spécifié par le premier opérande (assignation simple).|  
|**\*=**|Multiplie la valeur du premier opérande par la valeur du deuxième opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|`/=`|Divise la valeur du premier opérande par la valeur du deuxième opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|`%=`|Accepte le module du premier opérande spécifié par la valeur du deuxième opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|`+=`|Ajoute la valeur du deuxième opérande à la valeur du premier opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|**-=**|Soustrait la valeur du deuxième opérande de la valeur du premier opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|**<\<=**|Déplace la valeur du premier opérande à gauche du nombre de bits spécifiés par la valeur du deuxième opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|**>>=**|Déplace la valeur du premier opérande à droite du nombre de bits spécifiés par la valeur du deuxième opérande ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|**&=**|Obtient l’opérateur de bits AND du premier et du deuxième opérandes ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|`^=`|Obtient l’opérateur de bits OR exclusif du premier et du deuxième opérandes ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
|`&#124;=`|Obtient l’opérateur de bits OR inclusif du premier et du deuxième opérandes ; enregistre le résultat dans l’objet spécifié par le premier opérande.|  
  
 **Mots clés des opérateurs**  
  
 Trois des opérateurs d'assignation composée ont des équivalents textuels. Il s'agit des éléments suivants :  
  
|Opérateur|Équivalent|  
|--------------|----------------|  
|**&=**|`and_eq`|  
|`&#124;=`|`or_eq`|  
|`^=`|`xor_eq`|  
  
 Il existe deux façons d’accéder à ces mots clés des opérateurs dans vos programmes : incluez le fichier d’en-tête `iso646.h`, ou compilez avec le [/Za](../build/reference/za-ze-disable-language-extensions.md) option du compilateur (désactiver les extensions de langage).  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Assignment_Operators.cpp  
// compile with: /EHsc  
// Demonstrate assignment operators  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;  
  
   a += b;      // a is 9  
   b %= a;      // b is 6  
   c >>= 1;      // c is 5  
   d |= e;      // Bitwise--d is 0xFFFF   
  
   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl  
         << "a += b yields " << a << endl  
         << "b %= a yields " << b << endl  
         << "c >>= 1 yields " << c << endl  
         << "d |= e yields " << hex << d << endl;  
}  
```  
  
## <a name="simple-assignment"></a>Assignation simple  
 L'opérateur d'assignation simple (=) entraîne le stockage de la valeur du second opérande dans l'objet spécifié par le premier opérande. Si les deux objets sont de type arithmétique, l'opérande droit est converti en type de l'opérande gauche avant le stockage de la valeur.  
  
 Les objets de types const et volatile peuvent être assignés à des lvalues de types qui sont simplement volatile ou qui ne sont ni const ni volatile.  
  
 L'assignation à des objets de type classe (types struct, union et classe) est exécutée par une fonction nommée operator=. Le comportement par défaut de cette fonction d'opérateur consiste à effectuer une copie de bits ; toutefois, ce comportement peut être modifié à l'aide d'opérateurs surchargés. (Consultez [opérateurs surchargés](../cpp/operator-overloading.md) pour plus d’informations.)  
  
 Un objet de toute classe clairement dérivée d'une classe de base donnée peut être assigné à un objet de la classe de base. L'inverse n'est pas vrai, car il existe une conversion implicite de la classe dérivée vers la classe de base mais pas de la classe de base vers la classe dérivée. Exemple :  
  
```  
// expre_SimpleAssignment.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
class ABase  
{  
public:  
    ABase() { cout << "constructing ABase\n"; }  
};  
  
class ADerived : public ABase  
{  
public:  
    ADerived() { cout << "constructing ADerived\n"; }  
};  
  
int main()  
{  
    ABase aBase;  
    ADerived aDerived;  
  
    aBase = aDerived; // OK  
    aDerived = aBase; // C2679  
}  
```  
  
 Les assignations aux types référence se comportent comme si l'assignation était effectuée à l'objet auquel la référence pointe.  
  
 Pour les objets de type classe, l'assignation est différente de l'initialisation. Pour illustrer les différences entre l'assignation et l'initialisation, prenez le code  
  
```  
UserType1 A;  
UserType2 B = A;  
```  
  
 Le code précédent illustre un initialiseur ; il appelle le constructeur de `UserType2` qui accepte un argument de type `UserType1`. Étant donné le code  
  
```  
UserType1 A;  
UserType2 B;  
  
B = A;  
```  
  
 l'instruction d'assignation  
  
```  
B = A;   
```  
  
 peut avoir l'un des effets suivants :  
  
-   Appelez la fonction operator= pour `UserType2`, à condition que operator= possède un argument `UserType1`.  
  
-   Appelez la fonction de conversion explicite `UserType1::operator UserType2`, si une telle fonction existe.  
  
-   Appelez un constructeur `UserType2::UserType2`, si un tel constructeur existe, qui accepte un argument `UserType1` et copie le résultat.  
  
## <a name="compound-assignment"></a>Assignation composée  
 Les opérateurs d’assignation composée, affichés dans la table de [opérateurs d’assignation](../cpp/assignment-operators.md), sont spécifiés sous la forme *e1* `op` =  *e2*, où *e1* est une l-value modifiable pas de type const et *e2* est une des opérations suivantes :  
  
-   Un type arithmétique  
  
-   Un pointeur, si `op` est + ou -  
  
 Le *e1* `op` =  *e2* formulaire se comporte comme *e1* *= e1* `op` *e2*, mais *e1* est évaluée qu’une seule fois.  
  
 L'assignation composée en type énuméré génère un message d'erreur. Si l'opérande de gauche est d'un type pointeur, l'opérande de droite doit être d'un type pointeur ou il doit être une expression constante qui correspond à 0. Si l'opérande de gauche est d'un type intégral, l'opérande de droite ne doit pas être d'un type pointeur.  
  
## <a name="result-of-assignment-operators"></a>Résultat des opérateurs d'assignation  
 Les opérateurs d'assignation retournent la valeur de l'objet spécifié par l'opérande gauche après l'assignation. Le type résultant est le type de l'opérande gauche. Le résultat d'une expression d'assignation est toujours une l-value. Ces opérateurs ont une associativité de droite à gauche. L'opérande gauche doit être une l-value modifiable.  
  
 En C ANSI, le résultat d'une expression d'assignation n'est pas une l-value. Par conséquent, l'expression `(a += b) += c`, conforme dans C++, ne l'est pas dans C.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs d’assignation C](../c-language/c-assignment-operators.md)
