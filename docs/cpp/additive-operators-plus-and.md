---
title: "Opérateurs additifs : + et - | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '-'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- subtraction operator, additive operators
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
- '- operator, additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: 9
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
ms.openlocfilehash: a1017985934cbe871617b76f3e5959121b810602
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="additive-operators--and--"></a>Opérateurs additifs : + et -
## <a name="syntax"></a>Syntaxe  
  
```  
expression + expression   
expression - expression  
```  
  
## <a name="remarks"></a>Remarques  
 Les opérateurs additifs sont les suivants :  
  
-   Addition (**+**)  
  
-   Soustraction (**-**)  
  
 Ces opérateurs binaires ont une associativité de droite à gauche.  
  
 Les opérateurs additifs prennent des opérandes de type arithmétique ou pointeur. Le résultat de l’addition (**+**) (opérateur) est la somme des opérandes. Le résultat de la soustraction (**-**) (opérateur) est la différence entre les opérandes. Si l’un des opérandes ou les deux sont des pointeurs, ils doit d’agir de pointeurs vers des objets, et non des fonctions. Si les deux opérandes sont des pointeurs, les résultats ne sont pas significatifs à moins que tous deux ne soient des pointeurs vers des objets dans le même tableau.  
  
 Opérateurs additifs prennent des opérandes de *arithmétique*, *intégraux*, et *scalaire* types. Ils sont définis dans le tableau suivant.  
  
### <a name="types-used-with-additive-operators"></a>Types utilisés avec les opérateurs additifs  
  
|Type|Signification|  
|----------|-------------|  
|*opérations arithmétiques*|Les types intégraux et flottants sont appelés collectivement des types « arithmétiques ».|  
|*intégrale*|Les types char et int de toutes tailles (longs, courts) et les énumérations sont des types « intégraux ».|  
|*scalaire*|Les opérandes scalaires sont des opérandes de type arithmétique ou pointeur.|  
  
 Les combinaisons valides pour ces opérateurs sont les suivantes :  
  
 *arithmétique* + *arithmétique*  
  
 *scalaire* + *intégrale*  
  
 *intégraux* + *scalaire*  
  
 *arithmétique* - *arithmétique*  
  
 *scalaire* - *scalaire*  
  
 Notez que l'addition et la soustraction ne sont pas des opérations équivalentes.  
  
 Si les deux opérandes sont de type arithmétique, les conversions traitées dans [Conversions Standard](standard-conversions.md) sont appliquées aux opérandes, et le résultat est du type converti.  
  
## <a name="example"></a>Exemple  
  
```  
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## <a name="pointer-addition"></a>Addition de pointeur  
 Si l'un des opérandes d'une addition est un pointeur vers un tableau d'objets, l'autre doit être de type intégral. Le résultat est un pointeur qui est du même type que le pointeur d'origine et qui pointe vers un autre élément de tableau. Le fragment de code suivant illustre ce concept :  
  
```  
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 Bien que la valeur intégrale 1 soit ajoutée à `pIntArray`, cela ne signifie pas « ajouter 1 à l'adresse ». Cela signifie plutôt « ajuster le pointeur pour qu'il pointe vers l'objet suivant du tableau », qui se trouve à une distance de 2 octets (ou `sizeof( int )`).  
  
> [!NOTE]
>  Le code du formulaire `pIntArray = pIntArray + 1` figure rarement dans les programmes C++. Pour effectuer un incrément, il est préférable d'opter pour les formulaires `pIntArray++` ou `pIntArray += 1`.  
  
## <a name="pointer-subtraction"></a>Soustraction de pointeur  
 Si les deux opérandes sont des pointeurs, le résultat de la soustraction est la différence (en éléments de tableau) entre les opérandes. L'expression de soustraction génère un résultat intégral signé de type ptrdiff_t (défini dans le fichier Include standard STDDEF.H).  
  
 L'un des opérandes peut être de type intégral, à condition que ce soit le second opérande. Le résultat de la soustraction est du même type que le pointeur d'origine. La valeur de la soustraction est un pointeur vers la (*n* - *i*))-ième élément de tableau, où * n * est l’élément vers lequel pointe le pointeur d’origine et *i* la valeur intégrale du second opérande.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Les opérateurs C++ intégrés, priorité et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs additifs C](../c-language/c-additive-operators.md)
