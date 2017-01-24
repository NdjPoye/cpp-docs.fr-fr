---
title: "Avertissement du compilateur (niveau&#160;1) C4436 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4436
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le dynamic\_cast de base virtuelle « class1 » à « class2 » dans le constructeur ou le destructeur peut échouer avec un objet partiellement construit     Compiler avec \/vd2 ou définir « class2 » avec le vtordisp de \#pragma \(2\) activé  
  
 Le compilateur a rencontré une opération de `dynamic_cast` avec les caractéristiques suivantes.  
  
-   Le lancement consiste en un pointeur de base de la classe converti en un pointeur dérivé de la classe.  
  
-   La classe dérivée hérite pratiquement de la classe de base.  
  
-   La classe dérivée n'a aucun champ de `vtordisp` pour la base virtuelle.  
  
-   La conversion se trouve dans un constructeur ou un destructeur de la classe dérivée, ou d'une classe qui hérite davantage de la classe dérivée.  
  
 L'avertissement indique que le `dynamic_cast` peut ne pas s'exécuter correctement, s'il fonctionne sur un objet construit partiellement.  Cela se produit si le constructeur\/destructeur dérivé opère sur le type de sous\-objet d'un certain autre objet dérivé.  Si la classe dérivée nommée dans l'avertissement n'est jamais plus dérivée, l'avertissement peut être ignoré.  
  
## Exemple  
 L'échantillon suivant génère C4436 et illustre le problème de génération de code qui résulte du champ manquant `vtordisp`.  
  
```cpp  
// C4436.cpp  
// To see the warning and runtime assert, compile with: /W1  
// To eliminate the warning and assert, compile with: /W1 /vd2  
//       or compile with: /W1 /DFIX  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4436  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## Voir aussi  
 [dynamic\_cast, opérateur](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [Avertissement du compilateur \(niveau 4\) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)