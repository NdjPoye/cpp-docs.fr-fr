---
title: "&lt;chrono&gt; | Microsoft Docs"
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
  - "chrono/std::chrono::nanoseconds"
  - "chrono/std::chrono::minutes"
  - "chrono/std::chrono::seconds"
  - "<chrono>"
  - "chrono/std::chrono::hours"
  - "chrono/std::chrono::milliseconds"
  - "chrono/std::chrono::microseconds"
dev_langs: 
  - "C++"
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;chrono&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'en\-tête standard \<chrono\> pour définir des classes et des fonctions qui représentent et manipulent des durées et des instants.  
  
 **\(Visual Studio 2015 :\)** L'implémentation de `steady_clock` a changé pour satisfaire aux exigences de la norme C\+\+ en matière de stabilité et d'unitonicité.  `steady_clock` est maintenant basé sur QueryPerformanceCounter\(\) et `high_resolution_clock` est désormais un typedef pour `steady_clock`.  Ainsi, dans Visual C\+\+ `steady_clock::time_point` est désormais un typedef pour `chrono::time_point<steady_clock>`. Toutefois, cela n'est pas nécessairement le cas pour d'autres implémentations.  
  
## Syntaxe  
  
```cpp  
#include <chrono>  
```  
  
### Littéraux  
 Les littéraux dans l'en\-tête \<chrono\> sont des membres de l'espace de noms inline literals::chrono\_literals.  Pour plus d'informations, consultez [Littéraux chrono](../standard-library/chrono-literals.md).  
  
|||  
|-|-|  
|opérateur "" h\(unsigned long long Val\) opérateur "" h\(long double Val\)|Spécifie que la valeur représente des heures.|  
|opérateur "" min\(unsigned long long Val\)  opérateur "" min\(long double Val\)|Spécifie que la valeur représente des minutes.|  
|opérateur "" s\(unsigned long long Val\) opérateur "" s\(long double Val\)|Spécifie que la valeur représente des secondes.|  
|opérateur "" ms\(unsigned long long Val\) opérateur "" ms\(long double Val\)|Spécifie que la valeur représente des millisecondes.|  
|opérateur "" us\(unsigned long long Val\) opérateur "" us\(long double Val\)|Spécifie que la valeur représente des microsecondes.|  
|opérateur "" ns\(unsigned long long Val\) opérateur "" ns\(long double Val\)|Spécifie que la valeur représente des nanosecondes.|  
  
### Classes  
  
|Nom|Description|  
|---------|-----------------|  
|[duration, classe](../standard-library/duration-class.md)|Décrit un type qui contient un intervalle de temps.|  
|[time\_point, classe](../standard-library/time-point-class.md)|Décrit un type qui représente un point dans le temps.|  
  
### Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[common\_type, structure](../standard-library/common-type-structure.md)|Décrit les spécialisations de classe de modèle [common\_type](../standard-library/common-type-class.md) pour les instanciations de `duration` et `time_point`.|  
|[duration\_values, structure](../standard-library/duration-values-structure.md)|Fournit des valeurs spécifiques pour le paramètre de modèle `duration` `Rep`.|  
|[steady\_clock, struct](../standard-library/steady-clock-struct.md)|Représente une horloge `steady`.|  
|[system\_clock, structure](../standard-library/system-clock-structure.md)|Représente un *type d'horloge* basé sur l'horloge en temps réel du système.|  
|[treat\_as\_floating\_point, structure](../standard-library/treat-as-floating-point-structure.md)|Spécifie si un type peut être traité comme un type à virgule flottante.|  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[duration\_cast, fonction](../Topic/duration_cast%20Function.md)|Caste un objet `duration` en un type spécifié.|  
|[time\_point\_cast, fonction](../Topic/time_point_cast%20Function.md)|Caste un objet `time_point` en un type spécifié.|  
  
### Opérateurs  
  
|Nom|Description|  
|---------|-----------------|  
|[operator\-, opérateur \(STL\)](../Topic/operator-%20Operator%20\(STL\)1.md)|Opérateur de soustraction ou de négation d'objets `duration` et `time_point`.|  
|[operator\!\=, opérateur \(STL\)](../Topic/operator!=%20Operator%20\(STL\).md)|Opérateur d'inégalité utilisé avec des objets `duration` ou `time_point`.|  
|[opérateur modulo \(STL\)](../Topic/operator%20modulo%20\(STL\).md)|Opérateur pour opérations de modulo sur des objets `duration`.|  
|[operator\*, opérateur \(STL\)](../Topic/operator*%20Operator%20\(STL\).md)|Opérateur de multiplication pour les objets `duration`.|  
|[operator\/, opérateur \(STL\)](../Topic/operator-%20Operator%20\(STL\)2.md)|Opérateur de division pour les objets `duration`.|  
|[operator\+, opérateur \(STL\)](../Topic/operator+%20Operator%20\(STL\).md)|Ajoute des objets `duration` et `time_point`.|  
|[operator\<, opérateur \(STL\)](../Topic/operator%3C%20Operator%20\(STL\).md)|Détermine si un objet `duration` ou `time_point` est inférieur à un autre objet `duration` ou `time_point`.|  
|[operator\<\=, opérateur \(STL\)](../Topic/operator%3C=%20Operator%20\(STL\).md)|Détermine si un objet `duration` ou `time_point` est inférieur ou égal à un autre objet `duration` ou `time_point`.|  
|[operator\=\=, opérateur \(STL\)](../Topic/operator==%20Operator%20\(STL\).md)|Détermine si deux objets `duration` représentent des intervalles de temps de même longueur ou si deux objets `time_point` représentent le même point dans le temps.|  
|[operator\>, opérateur \(STL\)](../Topic/operator%3E%20Operator%20\(STL\).md)|Détermine si un objet `duration` ou `time_point` est supérieur à un autre objet `duration` ou `time_point`.|  
|[operator\>\= , opérateur \(STL\)](../Topic/operator%3E=%20Operator%20\(STL\).md)|Détermine si un objet `duration` ou `time_point` est supérieur ou égal à un autre objet `duration` ou `time_point`.|  
  
### Types de durée prédéfinis  
 Pour plus d'informations sur les types de rapports utilisés dans les typedefs suivants, consultez [\<ratio\>](../standard-library/ratio.md).  
  
|TypeDef|Description|  
|-------------|-----------------|  
|`typedef duration<long long, nano> nanoseconds;`|Synonyme pour un type `duration` qui a un cycle d'une nanoseconde.|  
|`typedef duration<long long, micro> microseconds;`|Synonyme pour un type `duration` qui a un cycle d'une microseconde.|  
|`typedef duration<long long, milli> milliseconds;`|Synonyme pour un type `duration` qui a un cycle d'une milliseconde.|  
|`typedef duration<long long> seconds;`|Synonyme pour un type `duration` qui a un cycle d'une seconde.|  
|`typedef duration<int, ratio<60> > minutes;`|Synonyme pour un type `duration` qui a un cycle d'une minute.|  
|`typedef duration<int, ratio<3600> > hours;`|Synonyme pour un type `duration` qui a un cycle d'une heure.|  
  
### Littéraux  
 **\(C\+\+11\)**L'en\-tête \<chrono\> définit les [littéraux définis par l'utilisateur](../cpp/user-defined-literals-cpp.md) suivants, que vous pouvez utiliser pour plus de commodité, pour la cohérence des types et pour faciliter la maintenance de votre code.  Ces littéraux sont définis dans l'espace de noms inline `literals::chrono_literals` et sont dans la portée quand std::chrono est dans la portée.  
  
|Littéral|Description|  
|--------------|-----------------|  
|chrono::hours opérateur "" h\(unsigned long long Val\)|Spécifie les heures comme valeur intégrale.|  
|chrono::duration\<double, ratio\<3600\> \> opérateur "" h\(long double Val\)|Spécifie les heures comme valeur à virgule flottante.|  
|chrono::minutes \(opérateur "" min\)\(unsigned long long Val\)|Spécifie les minutes comme valeur intégrale.|  
|chrono::duration\<double, ratio\<60\> \> \(opérateur "" min\)\( long double Val\)|Spécifie les minutes comme valeur à virgule flottante.|  
|chrono::seconds opérateur "" s\(unsigned long long Val\)|Spécifie les minutes comme valeur intégrale.|  
|chrono::duration\<double\> opérateur "" s\(long double Val\)|Spécifie les secondes comme valeur à virgule flottante.|  
|chrono::milliseconds opérateur "" ms\(unsigned long long \_Val\)|Spécifie les millisecondes comme valeur intégrale.|  
|chrono::duration\<double, milli\> opérateur "" ms\(long double \_Val\)|Spécifie les millisecondes comme valeur à virgule flottante.|  
|chrono::microseconds opérateur "" us\(unsigned long long Val\)|Spécifie les microsecondes comme valeur intégrale.|  
|chrono::duration\<double, micro\> opérateur "" us\(long double \_Val\)|Spécifie les microsecondes comme valeur à virgule flottante.|  
|chrono::nanoseconds opérateur "" ns\(unsigned long long \_Val\)|Spécifie les nanosecondes comme valeur intégrale.|  
|chrono::duration\<double, nano\> opérateur "" ns\(long double \_Val\)|Spécifie les nanosecondes comme valeur à virgule flottante.|  
|||  
  
## Notes  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)