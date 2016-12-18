---
title: "numeric_limits, classe | Microsoft Docs"
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
  - "std::numeric_limits"
  - "std.numeric_limits"
  - "numeric_limits"
  - "limits/std::numeric_limits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric_limits (classe)"
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# numeric_limits, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit les propriétés arithmétiques des types numériques intégrés.  
  
## Syntaxe  
  
```  
template<classType> class numeric_limits  
```  
  
#### Paramètres  
 `Type`  
 Type de données fondamental des éléments dont les propriétés sont testées, interrogées ou définies.  
  
## Notes  
 L'en\-tête définit des spécialisations explicites pour les types `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double`**,** `long long`, `unsigned long long`, `char16_t` et `char32_t`. Pour ces spécialisations explicites, le membre [numeric\_limits::is\_specialized](../Topic/numeric_limits::is_specialized.md) est `true`, et tous les membres pertinents ont des valeurs significatives. Le programme peut fournir des spécialisations explicites supplémentaires. La plupart des fonctions membres de la classe décrivent ou testent les implémentations possibles de `float`.  
  
 Pour une spécialisation arbitraire, aucun membre n'a de valeur significative. Un objet membre qui n'a pas de valeur significative stocke zéro \(ou `false`\), tandis qu'une fonction membre qui ne retourne pas de valeur significative retourne `Type(0)`.  
  
### Fonctions statiques et constantes  
  
|||  
|-|-|  
|[denorm\_min](../Topic/numeric_limits::denorm_min.md)|Retourne la plus petite valeur dénormalisée différente de zéro.|  
|[digits](../Topic/numeric_limits::digits.md)|Retourne le nombre de chiffres de base que le type peut représenter sans perte de précision.|  
|[digits10](../Topic/numeric_limits::digits10.md)|Retourne le nombre de chiffres décimaux que le type peut représenter sans perte de précision.|  
|[epsilon](../Topic/numeric_limits::epsilon.md)|Retourne la différence entre 1 et la plus petite valeur supérieure à 1 que le type de données peut représenter.|  
|[has\_denorm](../Topic/numeric_limits::has_denorm.md)|Teste si un type autorise les valeurs dénormalisées.|  
|[has\_denorm\_loss](../Topic/numeric_limits::has_denorm_loss.md)|Teste si une perte de précision est détectée comme une perte de dénormalisation et non pas comme un résultat inexact.|  
|[has\_infinity](../Topic/numeric_limits::has_infinity.md)|Teste si un type a une représentation pour l'infini positif.|  
|[has\_quiet\_NaN](../Topic/numeric_limits::has_quiet_NaN.md)|Teste si un type a une représentation pour un NaN \(n'est pas un nombre\) silencieux, qui ne fait pas de signalement.|  
|[has\_signaling\_NaN](../Topic/numeric_limits::has_signaling_NaN.md)|Teste si un type a une représentation pour signaler un NaN \(n'est pas un nombre\).|  
|[infinity](../Topic/numeric_limits::infinity.md)|Représentation de l'infini positif pour un type, si elle est disponible.|  
|[is\_bounded](../Topic/numeric_limits::is_bounded.md)|Teste si l'ensemble des valeurs qu'un type peut représenter est fini.|  
|[is\_exact](../Topic/numeric_limits::is_exact.md)|Teste si les calculs effectués sur un type ne comportent pas d'erreurs d'arrondi.|  
|[is\_iec559](../Topic/numeric_limits::is_iec559.md)|Teste si un type est conforme aux normes IEC 559.|  
|[is\_integer](../Topic/numeric_limits::is_integer.md)|Teste si un type a une représentation des entiers.|  
|[is\_modulo](../Topic/numeric_limits::is_modulo.md)|Teste si un type a une représentation du modulo.|  
|[is\_signed](../Topic/numeric_limits::is_signed.md)|Teste si un type a une représentation signée.|  
|[is\_specialized](../Topic/numeric_limits::is_specialized.md)|Teste si un type a une spécialisation explicite définie dans la classe de modèle `numeric_limits`.|  
|[lowest](../Topic/numeric_limits::lowest.md)|Retourne la plus grande valeur finie négative.|  
|[max](../Topic/numeric_limits::max.md)|Retourne la valeur finie maximale pour un type.|  
|[max\_digits10](../Topic/numeric_limits::max_digits10.md)|Retourne le nombre de chiffres décimaux requis pour garantir que deux valeurs distinctes du type ont des représentations décimales distinctes.|  
|[max\_exponent](../Topic/numeric_limits::max_exponent.md)|Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base \(radix\) est élevé à cette puissance.|  
|[max\_exponent10](../Topic/numeric_limits::max_exponent10.md)|Retourne l'exposant entier positif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base 10 est élevée à cette puissance.|  
|[min](../Topic/numeric_limits::min.md)|Retourne la valeur normalisée minimale pour un type.|  
|[min\_exponent](../Topic/numeric_limits::min_exponent.md)|Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand un nombre exprimé dans une base de base \(radix\) est élevé à cette puissance.|  
|[min\_exponent10](../Topic/numeric_limits::min_exponent10.md)|Retourne l'exposant entier négatif maximal que le type à virgule flottante peut représenter sous la forme d'une valeur finie quand une base 10 est élevée à cette puissance.|  
|[quiet\_NaN](../Topic/numeric_limits::quiet_NaN.md)|Retourne la représentation d'un NaN \(n'est pas un nombre\) silencieux pour le type.|  
|[radix](../Topic/numeric_limits::radix.md)|Retourne la base entière, appelée base \(radix\), utilisée pour la représentation d'un type.|  
|[round\_error](../Topic/numeric_limits::round_error.md)|Retourne l'erreur d'arrondi maximale pour le type.|  
|[round\_style](../Topic/numeric_limits::round_style.md)|Retourne une valeur qui décrit les différentes méthodes qu'une implémentation peut choisir pour arrondir une valeur à virgule flottante en valeur entière.|  
|[signaling\_NaN](../Topic/numeric_limits::signaling_NaN.md)|Retourne la représentation d'un NaN \(n'est pas un nombre\) avec signalement pour le type.|  
|[tinyness\_before](../Topic/numeric_limits::tinyness_before.md)|Teste si un type peut déterminer qu'une valeur est trop petite pour être représentée sous la forme d'une valeur normalisée avant d'être arrondie.|  
|[traps](../Topic/numeric_limits::traps.md)|Teste si les interceptions qui signalent des exceptions arithmétiques sont implémentées pour un type.|  
  
## Configuration requise  
 **En\-tête :** \<limites\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)