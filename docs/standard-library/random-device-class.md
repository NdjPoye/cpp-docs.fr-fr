---
title: "random_device, classe | Microsoft Docs"
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
  - "random_device"
  - "random/std::tr1::random_device"
  - "tr1.random_device"
  - "std::tr1::random_device"
  - "std.tr1.random_device"
  - "tr1::random_device"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "random_device (classe)"
  - "random_device (classe) (TR1)"
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: 27
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# random_device, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère une séquence aléatoire à partir d'un appareil externe.  
  
## Syntaxe  
  
```  
class random_device { public:     typedef unsigned int result_type;     // cosntructor     explicit random_device(const std::string& token = "");     // properties     static result_type min();     static result_type max();     double entropy() const;     // generate     result_type operator()();     // no-copy functions     random_device(const random_device&) = delete;     void operator=(const random_device&) = delete; };  
```  
  
## Membres  
  
|||  
|-|-|  
|[random\_device::random\_device](../Topic/random_device::random_device.md)|[random\_device::entropy](../Topic/random_device::entropy.md)|  
|[random\_device::operator\(\)](../Topic/random_device::operator\(\).md)||  
  
## Notes  
 La classe décrit une source de nombres aléatoires et a l'autorisation, sans y être obligée, d'être non déterministe ou sécurisée par chiffrement par la norme ISO C\+\+.  Dans l'implémentation Visual Studio, les valeurs produites sont non déterministes et sécurisées par chiffrement, mais elles sont exécutées plus lentement que les générateurs créés à partir de moteurs et d'adaptateurs de moteurs \(tels que [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md), le moteur rapide et de qualité élevée de choix pour la plupart des applications\).  
  
 Les résultats `random_device` sont distribués de manière uniforme dans la plage fermée \[`0, 2`<sup>32</sup>\).  
  
 Il n'est pas garanti que `random_device` aboutisse à un appel non bloquant.  
  
 Généralement, `random_device` est utilisé pour amorcer d'autres générateurs créés avec des moteurs ou adaptateurs de moteurs.  Pour plus d'informations, voir [\<random\>](../standard-library/random.md).  
  
## Exemple  
 Le code suivant illustre les fonctionnalités de base de cette classe et des exemples de résultats.  En raison de la nature non déterministe de `random_device`, les valeurs aléatoires affichées dans la section **Sortie** ne correspondent pas à vos résultats.  Cela est normal et prévu.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
 **Sortie :**  
  
  **entropie \=\= 32**  
**min \=\= 0**  
**max \=\= 4294967295**  
**10 valeurs aléatoires :**  
**4183829181**  
**1454391608**  
**1176278697**  
**2468830096**  
**3959347222**  
**1803123400**  
**1339590545**  
**1304896877**  
**604088490**  
**2293276253** Cet exemple est simpliste et ne représente pas le cas d'utilisation générale de ce générateur.  Pour obtenir un exemple de code plus représentatif, voir [\<random\>](../standard-library/random.md).  
  
## Configuration requise  
 **En\-tête :** \<random\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<random\>](../standard-library/random.md)