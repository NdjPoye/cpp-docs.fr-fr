---
title: "Op&#233;rateurs additifs&#160;: + et - | Microsoft Docs"
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
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "- (opérateur), opérateurs additifs en C++"
  - "+ (opérateur), opérateurs additifs"
  - "opérateurs additifs"
  - "opérateurs arithmétiques (C++), opérateurs additifs"
  - "opérateurs (C++), addition"
  - "soustraction (opérateur), opérateurs additifs"
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs additifs&#160;: + et -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
expression + expression   
expression – expression  
```  
  
## Notes  
 Les opérateurs additifs sont les suivants :  
  
-   Addition \(**\+**\)  
  
-   Soustraction \(**–**\)  
  
 Ces opérateurs binaires ont une associativité de droite à gauche.  
  
 Les opérateurs additifs prennent des opérandes de type arithmétique ou pointeur.  Le résultat de l'opérateur d'addition \(**\+**\) est la somme des opérandes.  Le résultat de l'opérateur de soustraction \(**–**\) est la différence entre les opérandes.  Si l'un des opérandes ou les deux sont des pointeurs, ils doit d'agir de pointeurs vers des objets, et non des fonctions.  Si les deux opérandes sont des pointeurs, les résultats ne sont pas significatifs à moins que tous deux ne soient des pointeurs vers des objets dans le même tableau.  
  
 Les opérateurs additifs prennent des opérandes de types *arithmétiques*, *intégraux* et *scalaires*.  Ils sont définis dans le tableau suivant.  
  
### Types utilisés avec les opérateurs additifs  
  
|Type|Signification|  
|----------|-------------------|  
|*arithmétique*|Les types intégraux et flottants sont appelés collectivement des types « arithmétiques ».|  
|*intégral*|Les types char et int de toutes tailles \(longs, courts\) et les énumérations sont des types « intégraux ».|  
|*scalaire*|Les opérandes scalaires sont des opérandes de type arithmétique ou pointeur.|  
  
 Les combinaisons valides pour ces opérateurs sont les suivantes :  
  
 *arithmétique* \+ *arithmétique*  
  
 *scalaire* \+ *intégral*  
  
 *intégral* \+ *scalaire*  
  
 *arithmétique* – *arithmétique*  
  
 *scalaire*  – *scalaire*  
  
 Notez que l'addition et la soustraction ne sont pas des opérations équivalentes.  
  
 Si les deux opérandes sont de type arithmétique, les conversions traitées dans [Conversions arithmétiques](../misc/arithmetic-conversions.md) sont appliquées aux opérandes et le résultat est du type converti.  
  
## Exemple  
  
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
  
## Addition de pointeur  
 Si l'un des opérandes d'une addition est un pointeur vers un tableau d'objets, l'autre doit être de type intégral.  Le résultat est un pointeur qui est du même type que le pointeur d'origine et qui pointe vers un autre élément de tableau.  Le fragment de code suivant illustre ce concept :  
  
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
  
 Bien que la valeur intégrale 1 soit ajoutée à `pIntArray`, cela ne signifie pas « ajouter 1 à l'adresse ». Cela signifie plutôt « ajuster le pointeur pour qu'il pointe vers l'objet suivant du tableau », qui se trouve à une distance de 2 octets \(ou `sizeof( int )`\).  
  
> [!NOTE]
>  Le code du formulaire `pIntArray = pIntArray + 1` figure rarement dans les programmes C\+\+. Pour effectuer un incrément, il est préférable d'opter pour les formulaires `pIntArray++` ou `pIntArray += 1`.  
  
## Soustraction de pointeur  
 Si les deux opérandes sont des pointeurs, le résultat de la soustraction est la différence \(en éléments de tableau\) entre les opérandes.  L'expression de soustraction génère un résultat intégral signé de type ptrdiff\_t \(défini dans le fichier Include standard STDDEF.H\).  
  
 L'un des opérandes peut être de type intégral, à condition que ce soit le second opérande.  Le résultat de la soustraction est du même type que le pointeur d'origine.  La valeur de la soustraction est un pointeur désignant le \(*n* – *i*\)\-ième élément de tableau, où *n* est l'élément désigné par le pointeur d'origine et *i* la valeur intégrale du second opérande.  
  
## Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Addition de types pointeur](../misc/addition-of-pointer-types.md)   
 [Soustraction de types pointeur](../misc/subtraction-of-pointer-types.md)   
 [Opérateurs additifs C](../c-language/c-additive-operators.md)