---
title: "complex&lt;double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.complex<double>"
  - "complex<double>"
  - "std::complex<double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonction de complexe < double >"
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# complex&lt;double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui stocke une paire ordonnée d'objets tous deux de type **double***,* le premier représentant la partie réelle d'un nombre complexe et le deuxième en représentant la partie imaginaire.  
  
## Syntaxe  
  
```  
template<>  
   class complex<double> {  
public:  
   constexpr complex(  
      double _RealVal = 0,   
      double _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr explicit complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Paramètres  
 `_RealVal`  
 La valeur de type **double** pour la partie réelle du nombre complexe à construire.  
  
 `_ImagVal`  
 La valeur de type **double** pour la partie imaginaire du nombre complexe à construire.  
  
 `_ComplexNum`  
 Nombre complexe de type **float** ou de type `long double` dont la partie réelle et la partie imaginaire sont utilisées pour initialiser le nombre complexe de type **double** qui est construit.  
  
## Valeur de retour  
 Nombre complexe de type **double**.  
  
## Notes  
 La spécialisation explicite de la classe de modèle complex en une classe complex de type **double** diffère de la classe de modèle seulement par les constructeurs qu'elle définit. La conversion de **float** en **double** peut être implicite, mais la conversion de `long double` en **double** doit être de type  **explicit**. L'utilisation de **explicit** exclut l'initialisation avec la conversion de type en utilisant une syntaxe d'affectation.  
  
 Pour plus d’informations sur la classe de modèle `complex`, consultez la page [complexe, classe](../standard-library/complex-class.md). Pour obtenir la liste des membres de la classe de modèle `complex`, consultez .  
  
## Exemple  
  
```  
// complex_comp_dbl.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type double gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 4.0 , 5.0 );  
   complex <double> c2double ( c2float );  
   cout << "Implicit conversion from type float to type double,"  
        << "\n gives c2double = " << c2double << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 4.0 , 5.0 );  
   complex <double> c3double ( c3longdouble );  
   cout << "Explicit conversion from type float to type double,"  
        << "\n gives c3longdouble = " << c3longdouble << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3longdouble );  
   double argc3 = arg ( c3longdouble );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
 **En spécifiant les parties réelles et imaginaires initiales, en tant que type double donne c1 \= \(4,5\) conversion implicite du type float au type double, donne c2double \= \(4,5\) conversion explicite du type float au type double, donne c3longdouble \= \(4,5\) le modulo de c3 est récupéré de c3 à l’aide : abs \(c3\) \= 6.40312 Argument C3 est récupéré de c3 à l’aide : arg \(c3\) \= 0.896055 radians, c'est\-à\-dire 51.3402 degrés.**   
## Configuration requise  
 **En\-tête :** \<complex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [complexe, classe](../standard-library/complex-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)