---
title: "Utilisation de fonctions lambda, d&#39;objets de fonctions et de fonctions restreintes | Microsoft Docs"
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
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 10
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de fonctions lambda, d&#39;objets de fonctions et de fonctions restreintes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le code C\+\+ AMP à exécuter sur l'accélérateur est spécifié en tant qu'argument dans un appel à la méthode [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).  Vous pouvez fournir soit une expression lambda, soit un objet de fonction \(functor\) en tant qu'argument.  En outre, l'expression lambda ou l'objet de fonction peut appeler une fonction restreinte C\+\+ AMP.  Cette rubrique utilise un algorithme d'addition de tableaux pour démontrer les expressions lambda, les objets de fonction et les fonctions restreintes.  L'exemple suivant illustre l'algorithme sans code C\+\+ AMP.  Deux tableaux unidimensionnels de longueur égale sont créés.  Les éléments entiers correspondants sont ajoutés et stockés dans un troisième tableau unidimensionnel.  C\+\+ AMP n'est pas utilisé.  
  
```cpp  
  
void CpuMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
## Expression lambda  
 Utiliser une expression lambda est la façon la plus directe d'utiliser C\+\+ AMP pour réécrire le code.  
  
```cpp  
  
void AddArraysWithLambda() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 L'expression lambda doit inclure un paramètre d'indexation, ainsi que `restrict(amp)`.  Dans l'exemple, l'objet [array\_view](../../parallel/amp/reference/array-view-class.md) `sum` a le rang 1.  Par conséquent, le paramètre de l'instruction lambda est un objet [index](../../parallel/amp/reference/index-class.md) ayant le rang 1.  Au moment de l'exécution, l'expression lambda est exécutée une fois pour chaque élément de l'objet [array\_view](../../parallel/amp/reference/array-view-class.md).  Pour plus d'informations, consultez [Syntaxe d'expression lambda](../../cpp/lambda-expression-syntax.md).  
  
## Function, objet  
 Il est possible de factoriser le code de l'accélérateur dans un objet de fonction.  
  
```cpp  
  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
        const array_view<int, 1>& b,  
        const array_view<int, 1>& sum  
    )  
    : a(a), b(b), sum(sum)  
    {  
    }  
  
    void operator()(index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
  
private:  
    array_view<int, 1> a;  
    array_view<int, 1> b;  
    array_view<int, 1> sum;  
};  
  
void AddArraysWithFunctionObject() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        AdditionFunctionObject(a, b, sum)  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 L'objet de fonction doit inclure un constructeur, ainsi qu'une surcharge de l'opérateur d'appel de fonction.  L'opérateur d'appel de fonction doit inclure un paramètre d'indexation.  Une instance de l'objet de fonction est passée comme deuxième argument à la méthode [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).  Dans cet exemple, trois objets [array\_view](../../parallel/amp/reference/array-view-class.md) sont passés au constructeur de l'objet de fonction.  L'objet [array\_view](../../parallel/amp/reference/array-view-class.md) `sum` a le rang 1.  Par conséquent, le paramètre de l'opérateur d'appel de fonction est un objet [index](../../parallel/amp/reference/index-class.md) ayant le rang 1.  Au moment de l'exécution, la fonction est exécutée une fois pour chaque élément de l'objet [array\_view](../../parallel/amp/reference/array-view-class.md).  Pour plus d’informations, consultez [Appel de fonction](../../cpp/function-call-cpp.md) et [objets de fonction dans la bibliothèque STL](../../standard-library/function-objects-in-the-stl.md).  
  
## Fonction restreinte C\+\+ AMP  
 Vous pouvez davantage factoriser le code d'accélérateur en créant une fonction restreinte et en l'appelant depuis une expression lambda ou un objet de fonction.  L'exemple de code suivant démontre comment appeler une fonction restreinte depuis une expression lambda.  
  
```cpp  
  
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            AddElementsWithRestrictedFunction(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 La fonction restreinte doit inclure `restrict(amp)` et être conforme aux restrictions décrites dans [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md).  
  
## Voir aussi  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Syntaxe d'expression lambda](../../cpp/lambda-expression-syntax.md)   
 [Appel de fonction](../../cpp/function-call-cpp.md)   
 [objets de fonction dans la bibliothèque STL](../../standard-library/function-objects-in-the-stl.md)   
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)