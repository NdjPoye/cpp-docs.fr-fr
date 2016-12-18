---
title: "seed_seq, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::seed_seq"
  - "std::tr1::seed_seq"
  - "tr1.seed_seq"
  - "seed_seq"
  - "std.tr1.seed_seq"
  - "random/std::tr1::seed_seq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "seed_seq (classe)"
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# seed_seq, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stocke un vecteur de valeurs entières non signées pouvant fournir une valeur initiale aléatoire pour un moteur de nombres aléatoires.  
  
## Syntaxe  
  
```  
class seed_seq  
{  
public:  
    // types  
    typedef unsigned int result_type;  
  
    // constructors  
    seed_seq();  
  
    template<class T>  
    seed_seq(initializer_list<T> initlist);  
  
    template<class InputIterator>  
    seed_seq(InputIterator begin, InputIterator end);  
  
    // generating functions  
    template<class RandomAccessIterator>  
    void generate(RandomAccessIterator begin, RandomAccessIterator end);  
  
    // property functions  
    size_t size() const;  
  
    template<class OutputIterator>  
    void param(OutputIterator dest) const;  
  
    // no copy functions  
    seed_seq(const seed_seq&) = delete;  
    void operator=(const seed_seq&) = delete;  
};  
```  
  
## Types  
 `typedef unsigned int result_type;`   
Le type des éléments de la séquence de valeurs. Un type entier non signé 32 bits.  
  
## Constructeurs  
 `seed_seq();`   
Constructeur par défaut initialise d’avoir une séquence interne vide.  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
Utilise `initlist` pour définir la séquence interne.  
`T` doit être un type entier.  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
Initialise la séquence interne à l’aide de tous les éléments de la plage d’itérateur d’entrée fournie.  
`iterator_traits<InputIterator>::value_type` doit être de type integer.  
  
## Membres  
  
### Fonctions de génération  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin, RandomAccessIterator end);`   
Remplit les éléments de la séquence fournie à l’aide d’un algorithme interne. Cet algorithme est affecté par la séquence interne avec laquelle `seed_seq` a été initialisée.  
Ne fait rien si `begin == end`.  
  
### Fonctions de propriétés  
 `size_t size() const;`   
Retourne le nombre d’éléments dans le `seed_seq`.  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
Copie la séquence interne dans l’itérateur de sortie `dest`.  
  
## Exemple  
 L'exemple de code suivant teste les trois constructeurs et génère une sortie à partir des instances `seed_seq` obtenues lors de l'assignation à un tableau. Pour obtenir un exemple qui utilise `seed_seq` avec un générateur de nombres aléatoires, consultez [\<random\>](../standard-library/random.md).  
  
```cpp  
#include <iostream>  
#include <random>  
#include <string>  
#include <array>  
  
using namespace std;  
  
void test(const seed_seq& sseq) {  
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;  
  
    cout << "seed_seq::param(): ";  
    ostream_iterator<unsigned int> out(cout, " ");  
    sseq.param(out);  
    cout << endl;  
  
    cout << "Generating a sequence of 5 elements into an array: " << endl;  
    array<unsigned int, 5> seq;  
    sseq.generate(seq.begin(), seq.end());  
    for (unsigned x : seq) { cout << x << endl; }  
}  
  
int main()  
{  
    seed_seq seed1;  
    test(seed1);  
  
    seed_seq seed2 = { 1701, 1729, 1791 };  
    test(seed2);  
  
    string sstr = "A B C D"; // seed string  
    seed_seq seed3(sstr.begin(), sstr.end());  
    test(seed3);  
}  
```  
  
## Sortie  
  
```Output  
  
seed_seq::Size() : seed_seq::param() 0 : génération d’une séquence de 5 éléments dans un tableau : 505382999 163489202 3932644188 763126080 73937346 seed_seq::size() : seed_seq::param() 3 : 1701 1 729 1791 générer une séquence de 5 éléments dans un tableau : 1730669648 1954224479 2809786021 1172893117 2393473414 seed_seq::size() : seed_seq::param() 7 : 65 32 66 32 32 67 68 générer une séquence de 5 éléments dans un tableau : 3139879222 3775111734 1084804564 2485037668 1985355432  
```  
  
## Notes  
 Fonctions membres de cette classe ne lèvent pas d’exceptions.  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)