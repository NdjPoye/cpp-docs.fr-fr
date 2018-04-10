---
title: arrêter d’instruction (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1f9c9a09652eb76511c7d059cc70eae3fb99ffd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="break-statement-c"></a>break, instruction (C++)
L'instruction `break` arrête l'exécution de la boucle englobante ou de l'instruction conditionnelle la plus proche dans laquelle elle apparaît. Le contrôle est passé à l'instruction qui suit l'instruction terminée, le cas échéant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
break;  
```  
  
## <a name="remarks"></a>Notes  
 Le `break` instruction est utilisée avec l’attribut conditional [commutateur](../cpp/switch-statement-cpp.md) instruction et avec le [faire](../cpp/do-while-statement-cpp.md), [pour](../cpp/for-statement-cpp.md), et [tandis que](../cpp/while-statement-cpp.md) boucle instructions.  
  
 Dans une instruction `switch`, l'instruction `break` entraîne l'exécution de la prochaine instruction située à l'extérieur de l'instruction `switch`. En l'absence d'une instruction `break`, toutes les instructions, depuis l'étiquette `case` correspondante jusqu'à la fin de l'instruction `switch`, y compris la clause `default`, sont exécutées.  
  
 Dans les boucles, l'instruction `break` arrête l'exécution de l'instruction englobante `do`, `for` ou `while` la plus proche. Le contrôle est passé à l'instruction qui suit l'instruction terminée, le cas échéant.  
  
 Dans les instructions imbriquées, l'instruction `break` arrête uniquement l'instruction `do`, `for`, `switch` ou `while` qui l'englobe directement. Utilisez une instruction `return` ou `goto` pour transférer le contrôle à partir des structures plus profondément imbriquées.  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser l'instruction `break` dans une boucle `for`.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
```Output  
In each case:   
1  
2  
3  
```  
  
 Le code suivant montre comment utiliser l'instruction `break` dans une boucle `while` et une boucle `do`.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
```Output  
In each case:  
0123  
```  
  
 Le code suivant montre comment utiliser l'instruction `break` dans une instruction switch. Vous devez utiliser une instruction `break` pour traiter chaque cas séparément. Si vous n'utilisez pas une instruction `break`, l'exécution du code passera au cas suivant.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [Instruction continue](../cpp/continue-statement-cpp.md)