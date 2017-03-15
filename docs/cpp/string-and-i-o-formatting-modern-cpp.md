---
title: "Mise en forme des cha&#238;nes et E/S (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise en forme des cha&#238;nes et E/S (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les [iostreams](../standard-library/iostream.md) C\+\+ sont capables de mettre en forme les E\/S de chaîne.  Par exemple, le code suivant indique comment définir cout pour mettre en forme un entier à sortir au format hexadécimal, en enregistrant d'abord l'état actuel et en le redéfinissant ensuite, car une fois que la mise en forme de l'état est passée à cout, l'ensemble du code reste ainsi jusqu'à modification.  
  
```fortran  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
int main()   
{  
    ios state(nullptr);  
  
    cout << "The answer in decimal is: " << 42 << endl;  
  
    state.copyfmt(cout); // save current formatting  
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers  
        << hex   
        << uppercase   
        << setw(8)   
        << setfill('0')   
        << 42            // the actual value we wanted to print out  
        << endl;  
    cout.copyfmt(state); // restore previous formatting  
}  
  
```  
  
 Cela peut être réellement trop fastidieux dans de nombreux cas.  Vous pouvez aussi utiliser Boost.Format des bibliothèques Boost C\+\+, même s'il n'est pas standard.  Vous pouvez télécharger une bibliothèque Boost depuis le site Web [Boost](http://www.boost.org/).  
  
 Voici certains avantages de Boost.Format :  
  
-   Sécurisé : type sécurisé. Lève une exception pour les erreurs \(par exemple, la spécification d'un trop petit nombre ou d'un trop grand nombre d'éléments\).  
  
-   Extensible : fonctionne pour tout type qui peut être transmis en continu.  
  
-   Pratique : norme Posix standard et chaînes de format similaires.  
  
 Bien que Boost.Format soit généré en C\+\+ [iostreams](../standard-library/iostream-programming.md), qui est sécurisé et extensible, il n'est pas optimisé pour les performances.  Lorsque vous exigez une optimisation des performances, considérez en C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) et [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), qui sont rapides et faciles à utiliser.  Toutefois, ils ne sont pas extensibles ou protégés contre les vulnérabilités. Les versions sécurisées existent, mais elles réduisent légèrement les performances.  Pour plus d’informations, consultez [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) et [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)\).  
  
 Le code suivant illustre quelques\-unes des fonctionnalités de mise en forme de Boost.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)   
 [\<iostream\>](../standard-library/iostream.md)   
 [\<limits\>](../standard-library/limits.md)   
 [\< iomanip \>](../standard-library/iomanip.md)