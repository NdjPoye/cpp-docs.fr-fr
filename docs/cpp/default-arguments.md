---
title: "Arguments par défaut | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88c341abab34595da58d435be28f50e86cb47403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="default-arguments"></a>Arguments par défaut
Dans de nombreux cas, les fonctions ont des arguments utilisés si rarement qu’une valeur par défaut suffirait. La fonctionnalité d’argument par défaut permet de spécifier uniquement les arguments d’une fonction qui sont significatifs dans un appel donné. Pour illustrer ce concept, prenons l’exemple présenté dans [surcharge de fonction](../cpp/function-overloading.md).  
  
```  
// Prototype three print functions.  
int print( char *s );                  // Print a string.  
int print( double dvalue );            // Print a double.  
int print( double dvalue, int prec );  // Print a double with a  
//  given precision.  
```  
  
 Dans de nombreuses applications, une valeur par défaut raisonnable peut être fournie pour `prec`, éliminant ainsi la nécessité de faire appel à deux fonctions :  
  
```  
// Prototype two print functions.  
int print( char *s );                    // Print a string.  
int print( double dvalue, int prec=2 );  // Print a double with a  
//  given precision.  
```  
  
 L’implémentation de la `print` fonction est légèrement modifiée pour refléter le fait que seule une telle fonction existe pour le type **double**:  
  
```  
// default_arguments.cpp  
// compile with: /EHsc /c  
  
// Print a double in specified precision.  
//  Positive numbers for precision indicate how many digits  
//  precision after the decimal point to show. Negative  
//  numbers for precision indicate where to round the number  
//  to the left of the decimal point.  
  
#include <iostream>  
#include <math.h>  
using namespace std;  
  
int print( double dvalue, int prec ) {  
   // Use table-lookup for rounding/truncation.  
   static const double rgPow10[] = {   
      10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,  
         10E1,  10E2,  10E3,  10E4, 10E5,  10E6  
   };  
   const int iPowZero = 6;  
   // If precision out of range, just print the number.  
   if( prec >= -6 && prec <= 7 )  
      // Scale, truncate, then rescale.  
      dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *  
      rgPow10[iPowZero - prec];  
   cout << dvalue << endl;  
   return cout.good();  
}  
```  
  
 Pour appeler la nouvelle fonction `print`, utilisez du code comme semblable au suivant :  
  
```  
print( d );    // Precision of 2 supplied by default argument.  
print( d, 0 ); // Override default argument to achieve other  
//  results.  
```  
  
 Tenez compte des points suivants lors de l'utilisation des arguments par défaut :  
  
-   Les arguments par défaut sont utilisés uniquement dans les appels de fonction où les arguments de fin sont omis. Il doit s’agir des derniers arguments. Par conséquent, le code suivant n'est pas valide :  
  
    ```  
    int print( double dvalue = 0.0, int prec );  
    ```  
  
-   Un argument par défaut ne peut pas être redéfini dans des déclarations ultérieures, même si la redéfinition est identique à celle d'origine. Par conséquent, le code suivant génère une erreur :  
  
    ```  
    // Prototype for print function.  
    int print( double dvalue, int prec = 2 );  
  
    ...  
  
    // Definition for print function.  
    int print( double dvalue, int prec = 2 )  
    {  
    ...  
    }  
    ```  
  
     Le problème avec ce code est que la déclaration de fonction dans la définition redéfinit l'argument par défaut pour `prec`.  
  
-   Des arguments par défaut supplémentaires peuvent être ajoutés par des déclarations ultérieures.  
  
-   Des arguments par défaut peuvent être fournis pour des pointeurs vers des fonctions. Exemple :  
  
    ```  
    int (*pShowIntVal)( int i = 0 );  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 