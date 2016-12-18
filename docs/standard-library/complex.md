---
title: "&lt;complex&gt; | Microsoft Docs"
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
  - "<complex>"
  - "std.<complex>"
  - "std::<complex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête complexe"
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;complex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle de conteneur complex et ses modèles de prise en charge.  
  
## Syntaxe  
  
```  
  
#include <complex>  
  
```  
  
## Notes  
 Un nombre complexe est une paire ordonnée de nombres réels.  En termes purement géométriques, le plan complexe est le plan réel à deux dimensions.  Les qualités spéciales du plan complexe qui le distinguent du plan réel sont dues au fait qu'il a une structure algébrique supplémentaire.  Cette structure algébrique a deux opérations fondamentales :  
  
-   L'addition, définie comme \(*a, b*\) \+ \(*c, d*\) \= \(*a\+ c, b \+ d\)*  
  
-   La multiplication, définie comme \(*a, b*\) \* \(*c, d*\) \= \(*ac \- bd, ad \+ bc*\)  
  
 L'ensemble de nombres complexes avec les opérations d'addition complexe et de multiplication complexe est un domaine au sens algébrique standard :  
  
-   Les opérations d'addition et multiplication sont commutatives et associatives, et la multiplication se distribue sur l'addition exactement comme elle le fait avec l'addition et la multiplication de réels sur le domaine des nombres réels.  
  
-   Le nombre complexe \(*0, 0*\) est l'identité additive et \(*1, 0*\) est l'identité multiplicative.  
  
-   L'inverse additif d'un nombre complexe \(*a, b*\) est \(*\-a, \-b*\) et l'inverse multiplicatif pour tous les nombres complexes excepté \(*0, 0*\) est  
  
     \(*a*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\), \-*b*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\)  
  
 En représentant un nombre complexe *z \= \(a, b\)* sous la forme *z \= a \+ bi,*  où *i*<sup>2</sup> *\=* \-1, les règles de l'algèbre de l'ensemble des nombres réels peuvent être appliquées à l'ensemble des nombres complexes et à leurs composants.  Par exemple :  
  
 \(1 \+ 2*i*\) \* \(2 \+ 3*i*\)    \= 1\*\(2 \+ 3*i*\) \+ 2*i*\*\(2 \+ 3*i*\) \= \(2 \+ 3*i*\) \+ \(4*i* \+ 6*i*<sup>2</sup>\)  
  
 \= \(2 –6\) \+ \(3 \+ 4\)*i* \= \-4 \+ 7*i*  
  
 Le système des nombres complexes est un domaine, mais il n'est pas un domaine ordonné.  Il n'existe pas d'ordonnancement des nombres complexes comme c'est le cas pour le domaine des nombres réels et de ses sous\-ensembles : les inégalités ne peuvent donc pas être appliquées aux nombres complexes comme c'est le cas des nombres réels, qui constituent un domaine ordonné.  
  
 Il existe trois formes courantes de représentation d'un nombre complexe *z* :  
  
-   Cartésienne : *z \= a \+ bi*  
  
-   Polaire : *z \= r* \(cos *\+ i*sin\)  
  
-   Exponentielle :*z \= r \** exp\(\)  
  
 Les termes utilisés dans ces représentations standard d'un nombre complexe s'entendent comme suit :  
  
-   Le composant cartésien réel ou la partie réelle *a*.  
  
-   Le composant imaginaire cartésien ou la partie imaginaire *b*.  
  
-   Le module ou la valeur absolue d'un nombre complexe P.  
  
-   L'argument ou angle de phase.  
  
 Sauf indication contraire, les fonctions qui peuvent retourner plusieurs valeurs doivent retourner une valeur principale pour leurs arguments supérieure à –pi, et inférieures ou égales à \+pi, pour les conserver avec une valeur unique.  Tous les angles doivent être exprimés en radians, avec 2 pi radians \(360 degrés\) dans un cercle.  
  
### Fonctions  
  
|||  
|-|-|  
|[abs](../Topic/abs.md)|Calcule le module d'un nombre complexe.|  
|[arg](../Topic/arg.md)|Extrait l'argument d'un nombre complexe.|  
|[conj](../Topic/conj.md)|Retourne le conjugué complexe d'un nombre complexe.|  
|[cos](../Topic/cos.md)|Retourne le cosinus d'un nombre complexe.|  
|[cosh](../Topic/cosh.md)|Retourne le cosinus hyperbolique d'un nombre complexe.|  
|[exp](../Topic/exp.md)|Retourne la fonction exponentielle d'un nombre complexe.|  
|[imag](../Topic/imag.md)|Extrait le composant imaginaire d'un nombre complexe.|  
|[log](../Topic/log.md)|Retourne le logarithme naturel d'un nombre complexe.|  
|[log10](../Topic/log10.md)|Retourne le logarithme de base 10 d'un nombre complexe.|  
|[norm](../Topic/norm.md)|Extrait la norme d'un nombre complexe.|  
|[polar](../Topic/polar.md)|Retourne le nombre complexe qui correspond à un module et à un argument spécifiés, au format cartésien.|  
|[pow](../Topic/pow.md)|Évalue le nombre complexe obtenu en élevant une base qui est un nombre complexe à la puissance d'un autre nombre complexe.|  
|[réels](../Topic/real.md)|Extrait le composant réel d'un nombre complexe.|  
|[sin](../Topic/sin.md)|Retourne le sinus d'un nombre complexe.|  
|[sinh](../Topic/sinh.md)|Retourne le sinus hyperbolique d'un nombre complexe.|  
|[sqrt](../Topic/sqrt.md)|Retourne la racine carrée d'un nombre complexe.|  
|[tan](../Topic/Functions%20tan.md)|Retourne la tangente d'un nombre complexe.|  
|[tanh](../Topic/tanh.md)|Retourne la tangente hyperbolique d'un nombre complexe.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\!\=, opérateur](../Topic/operator!=%20\(%3Ccomplex%3E\).md)|Vérifie l'inégalité entre deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[operator\*](../Topic/operator*%20\(%3Ccomplex%3E\).md)|Multiplie deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[operator\+](../Topic/operator+%20\(%3Ccomplex%3E\).md)|Additionne deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[operator\-](../Topic/operator-%20\(%3Ccomplex%3E\)1.md)|Soustrait deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[operator\/](../Topic/operator-%20\(%3Ccomplex%3E\)2.md)|Divise deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[\<\<, opérateur](../Topic/operator%3C%3C%20\(%3Ccomplex%3E\).md)|Fonction de modèle qui insère un nombre complexe dans le flux de sortie.|  
|[operator\=\=](../Topic/operator==%20\(%3Ccomplex%3E\).md)|Vérifie l'égalité entre deux nombres complexes, l'un d'entre eux ou les deux pouvant appartenir au sous\-ensemble du type pour les parties réelles et imaginaires.|  
|[\>\>, opérateur](../Topic/operator%3E%3E%20\(%3Ccomplex%3E\).md)|Fonction de modèle qui extrait un nombre complexe du flux d'entrée.|  
  
### Classes  
  
|||  
|-|-|  
|[complex\<double\>](../standard-library/complex-double.md)|La classe de modèle explicitement spécialisée décrit un objet qui stocke une paire ordonnée d'objets tous deux de type **double***,* le premier représentant la partie réelle d'un nombre complexe et le deuxième en représentant la partie imaginaire.|  
|[complex\<float\>](../standard-library/complex-float.md)|La classe de modèle explicitement spécialisée décrit un objet qui stocke une paire ordonnée d'objets tous deux de type **float***,* le premier représentant la partie réelle d'un nombre complexe et le deuxième en représentant la partie imaginaire.|  
|[complex\<long double\>](../standard-library/complex-long-double.md)|La classe de modèle explicitement spécialisée décrit un objet qui stocke une paire ordonnée d'objets tous deux de type `long double`*,* le premier représentant la partie réelle d'un nombre complexe et le deuxième en représentant la partie imaginaire.|  
|[complexes](../standard-library/complex-class.md)|La classe de modèle décrit un objet utilisé pour représenter le système des nombres complexes et pour effectuer des opérations arithmétiques complexes.|  
  
### Littéraux  
 L'en\-tête \<complex\> définit les [littéraux définis par l'utilisateur](../cpp/user-defined-literals-cpp.md) suivants, qui créent un nombre complexe avec la partie réelle valant zéro et la partie imaginaire étant la valeur du paramètre d'entrée.  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|Retourne `complex<long double>{0.0L, static_cast<long double>(d)}`.|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Retourne : `complex<double>{0.0, static_cast<double>(d)}`.|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Retourne : `complex<float>{0.0f, static_cast<float>(d)}`.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)