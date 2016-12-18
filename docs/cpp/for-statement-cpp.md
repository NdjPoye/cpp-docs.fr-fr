---
title: "for, instruction (C++) | Microsoft Docs"
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
  - "for (mot clé) (C++)"
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute une instruction à plusieurs reprises jusqu'à ce que la condition soit false.  Pour plus d'informations sur les instructions For basées sur une plage, consultez [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md).  
  
## Syntaxe  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## Notes  
 Utilisez l'instruction `for` pour créer des boucles qui doivent être exécutées un certain nombre de fois.  
  
 L'instruction `for` se compose de trois parties facultatives, comme indiqué dans le tableau suivant.  
  
### Éléments de boucle For  
  
|Nom de la syntaxe|Moment de l'exécution|Description|  
|-----------------------|---------------------------|-----------------|  
|`init-expression`|`init-expression` est exécuté une seule fois avant tous les autres éléments de l'instruction **for**.  Le contrôle passe alors à `cond-expression`.|Souvent employé pour initialiser des index de boucle.  Elle peut contenir des expressions ou des déclarations.|  
|`cond-expression`|Avant l'exécution de chaque itération de `statement`, y compris la première itération.  `statement` est exécuté uniquement si `cond-expression` a la valeur true \(valeur différente de zéro\).|Expression qui correspond à un type intégral ou à un type de classe avec une conversion non ambiguë en type intégral.  Normalement utilisée pour déterminer les critères d'arrêts de boucles.|  
|`loop-expression`|À la fin de chaque itération de `statement`.  `cond-expression` est évalué après l'exécution de `loop-expression`.|Normalement utilisée pour incrémenter les index de boucle.|  
  
 Les exemples suivants montrent diverses façons d'utiliser l'instruction `for`.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` et `loop-expression` peuvent contenir plusieurs instructions séparées par des virgules.  Par exemple :  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression` peut être incrémenté ou décrémenté, ou autrement modifié.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 Une boucle `for` se termine lorsqu'une instruction [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md) ou [goto](../cpp/goto-statement-cpp.md) \(vers une instruction étiquetée extérieure à la boucle **for**\) contenue dans `statement` est exécutée.  Une instruction [continue](../cpp/continue-statement-cpp.md) contenue dans une boucle `for` termine uniquement l'itération en cours.  
  
 Si `cond-expression` est omis, il sera considéré comme true, et la boucle **for** ne se terminera pas sans une instruction `break`, `return` ou `goto` contenue dans `statement`.  
  
 Bien que les trois champs de l'instruction `for` soient normalement utilisés pour l'initialisation, les tests de fin et l'incrémentation, ils ne sont pas limités à ces applications.  Par exemple, le code suivant affiche les nombres 0 à 4.  Dans ce cas, `statement` est l'instruction null :  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## Boucles for et norme C\+\+  
 Selon la norme C\+\+, une variable déclarée dans une boucle `for` passe hors de portée lorsque la boucle `for` est terminée.  Par exemple :  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 Par défaut, sous [\/Ze](../build/reference/za-ze-disable-language-extensions.md), une variable déclarée dans une boucle `for` reste dans la portée jusqu'à ce que la portée englobante de la boucle `for` soit terminée.  
  
 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) active le comportement standard des variables déclarées dans des boucles sans que la spécification de \/Za ne soit nécessaire.  
  
 Il est également possible d'utiliser les différences de portée de la boucle `for` pour redéclarer des variables sous \/Ze comme suit :  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Cela reproduit plus fidèlement le comportement standard d'une variable déclarée dans une boucle `for`, qui requiert des variables déclarées dans une boucle `for` pour sortir de la portée lorsque la boucle est terminée.  Lorsqu'une variable est déclarée dans une boucle `for`, le compilateur la convertit en interne en variable locale dans la portée englobante de la boucle `for`, même s'il existe déjà une variable locale du même nom.  
  
## Voir aussi  
 [Instructions d'itération](../cpp/iteration-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [while, instruction \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [do\-while, instruction \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)