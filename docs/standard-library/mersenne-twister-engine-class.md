---
title: "mersenne_twister_engine, classe | Microsoft Docs"
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
  - "random/std::tr1::mersenne_twister_engine"
  - "tr1.mersenne_twister_engine"
  - "std.tr1.mersenne_twister_engine"
  - "std::tr1::mersenne_twister_engine"
  - "tr1::mersenne_twister_engine"
  - "mersenne_twister_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mersenne_twister_engine (classe)"
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
caps.latest.revision: 23
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mersenne_twister_engine, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire d'entiers de haute qualité selon l'algorithme twister de Mersenne.  
  
## Syntaxe  
  
```  
template<class UIntType,   
    size_t W, size_t N, size_t M, size_t R,  
    UIntType A, size_t U, UIntType D, size_t S,  
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>  
class mersenne_twister_engine;  
```  
  
#### Paramètres  
 `UIntType`  
 Type des résultats entiers non signés. Pour les types possibles, consultez la page [\<random\>](../standard-library/random.md).  
  
 `W`  
 **Taille de mot**. Taille de chaque mot, en bits, de la séquence d'état.**Condition préalable** : `2u < W ≤ numeric_limits<UIntType>::digits`  
  
 `N`  
 **Taille de l'état**. Nombre d'éléments \(valeurs\) dans la séquence d'état.  
  
 `M`  
 **Taille de décalage**. Nombre d'éléments à ignorer pendant chaque torsion.**Condition préalable** : `0 < M ≤ N`  
  
 `R`  
 **Bits du masque**.**Condition préalable** : `R ≤ W`  
  
 `A`  
 **Masque XOR**.**Condition préalable** : `A ≤ (1u<<W) - 1u`  
  
 `U`, `S`, `T`, `L`  
 **Paramètres de décalage d'altération**. Utilisés comme valeurs de décalage pendant le brouillage \(altération\). Condition préalable :`U,S,T,L ≤ W`  
  
 `D`, `B`, `C`  
 **Paramètres de masque de bits d'altération**. Utilisés comme valeurs de masque de bits pendant le brouillage \(altération\). Condition préalable :`D,B,C ≤ (1u<<W) - 1u`  
  
 `F`  
 **Multiplicateur d'initialisation**. Aide à l'initialisation de la séquence. Condition préalable :`F ≤ (1u<<W) - 1u`  
  
## Membres  
  
||||  
|-|-|-|  
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|  
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|  
  
 `default_seed` est une constante membre, définie comme `5489u`, utilisée comme valeur de paramètre par défaut pour `mersenne_twister_engine::seed` et le constructeur de valeur unique.  
  
 Pour plus d’informations sur les membres moteurs, consultez [\<random\>](../standard-library/random.md).  
  
## Notes  
 Cette classe de modèle décrit un moteur de nombres aléatoires, qui retournent des valeurs dans l’intervalle fermé \[`0`, `2`<sup>W</sup> \- `1`\]. Il contient une valeur intégrale élevée avec `W * (N - 1) + R` bits. Il extrait `W` bits à la fois de cette valeur élevée et, quand il a utilisé tous les bits, il déforme la valeur élevée en décalant et en combinant les bits pour avoir un nouvel ensemble de bits dans lequel procéder à l'extraction. L’état du moteur est le dernier `N``W`\-bits utilisées si `operator()` a été appelé au moins `N` fois, sinon le `M``W`\-bit des valeurs qui ont été utilisées et le dernier `N - M` les valeurs de la valeur initiale.  
  
 Le générateur déforme la valeur élevée qu'il contient en utilisant un registre à décalage de commentaires généralisés déformés défini par les valeurs de décalage `N` et `M`, une valeur de torsion `R` et un masque XOR conditionnel `A`. En outre, les bits du registre à décalage brut sont brouillés \(altérés\) selon une matrice de brouillage des bits définie par les valeurs `U`, `D`, `S`, `B`, `T`, `C` et `L`.  
  
 L’argument template `UIntType` doit être suffisamment grande pour contenir des valeurs jusqu'à `2`<sup>W</sup> \- `1`. Les valeurs des autres arguments de modèle doivent être conformes aux spécifications suivantes : `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.  
  
 Bien que vous puissiez construire un générateur à partir de ce moteur directement, il est recommandé de qu'utiliser une de ces typedefs prédéfinis :  
  
 `mt19937`: moteur de twister Mersenne 32 bits \(Matsumoto et Nishimura, 1998\).  
  
```  
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,   
    31, 0x9908b0df,   
    11, 0xffffffff,   
    7, 0x9d2c5680,   
    15, 0xefc60000,   
    18, 1812433253> mt19937;  
```  
  
 `mt19937_64`: moteur de twister Mersenne 64 bits \(Matsumoto et Nishimura, 2000\).  
  
```  
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,   
    31, 0xb5026f5aa96619e9ULL,   
    29, 0x5555555555555555ULL,   
    17, 0x71d67fffeda60000ULL,   
    37, 0xfff7eee000000000ULL,   
    43, 6364136223846793005ULL> mt19937_64;  
```  
  
 Pour plus d’informations sur l’algorithme twister de Mersenne, voir l’article de Wikipedia [Mersenne twister](http://go.microsoft.com/fwlink/?LinkId=402356).  
  
## Exemple  
 Pour obtenir un exemple de code, consultez [\<random\>](../standard-library/random.md).  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)