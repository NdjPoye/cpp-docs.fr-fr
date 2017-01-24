---
title: "Avertissement du compilateur (niveau&#160;4) C4437 | Microsoft Docs"
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
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4437
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le dynamic\_cast de la base virtuelle « class1 » à « class2 » peut échouer dans certains contextes      Compilez avec \/vd2 ou définissez « class2 » avec le vtordisp de \#pragma \(2\) activé  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Le compilateur a rencontré une opération de `dynamic_cast` avec les caractéristiques suivantes.  
  
-   Le cast consiste en un pointeur de base de la classe converti en un pointeur dérivé de la classe.  
  
-   La classe dérivée hérite pratiquement de la classe de base.  
  
-   La classe dérivée n'a aucun champ de `vtordisp` pour la base virtuelle.  
  
-   La conversion est introuvable dans un constructeur ou un destructeur de la classe dérivée, ou d'une classe qui hérite davantage de la classe dérivée \(dans le cas contraire, l'avertissement du compilateur C4436 est émis\).  
  
 L'avertissement indique que le `dynamic_cast` peut ne pas s'exécuter correctement s'il fonctionne sur un objet construit partiellement.  Cette situation se produit lorsque la fonction englobante est appelée d'un constructeur ou d'un destructeur d'une classe qui hérite de la classe dérivée nommée dans l'avertissement.  Si la classe dérivée nommée dans l'avertissement n'est jamais dérivée davantage, ou si la fonction englobante n'est pas appelée pendant la construction ou la destruction de l'objet, l'avertissement peut être ignoré.  
  
## Exemple  
 L'échantillon suivant génère l'erreur C4437 et illustre le problème de génération de code qui résulte du champ manquant de `vtordisp`.  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
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
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
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
 [Avertissement du compilateur \(niveau 1\) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)