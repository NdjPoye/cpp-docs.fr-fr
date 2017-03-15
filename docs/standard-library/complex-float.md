---
title: "complex&lt;float&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::complex<float>"
  - "std.complex<float>"
  - "complex<float>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex<float> (fonction)"
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# complex&lt;float&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui stocke une paire ordonnée d'objets de type **float***,* le premier représentant la partie réelle d'un nombre complexe et le deuxième représentant la partie imaginaire.  
  
## Syntaxe  
  
```  
template<>  
   class complex<float> {  
public:  
   constexpr complex(  
      float _RealVal = 0,   
      float _ImagVal = 0  
   );  
  
   constexpr complex(  
      const complex<float>& _ComplexNum  
   );  
   constexpr complex(  
      const complex<double>& _ComplexNum  
   );  
   constexpr complex(  
      const complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Paramètres  
 `_RealVal`  
 Valeur de type **float** pour la partie réelle du nombre complexe qui est construit.  
  
 `_ImagVal`  
 Valeur de type **float** pour la partie imaginaire du nombre complexe qui est construit.  
  
 `_ComplexNum`  
 Nombre complexe de type **double** ou de type `long double` dont les parties réelle et imaginaire sont utilisées pour initialiser un nombre complexe de type **float** en cours de construction.  
  
## Valeur de retour  
 Nombre complexe de type **float**.  
  
## Notes  
 La spécialisation explicite de la classe de modèle complex en une classe complexe de type **float** diffère de la classe de modèle uniquement dans les constructeurs qu'elle définit.  La conversion de **float** en **double** peut être implicite, mais la conversion moins sécurisée de **float** en `long double` doit être de type **explicit**.  L'utilisation de **explicit** exclut l'initialisation avec la conversion de type en utilisant une syntaxe d'affectation.  
  
 Pour plus d'informations sur la classe de modèle `complex`, consultez [complexe, classe](../standard-library/complex-class.md).  Pour obtenir une liste des membres de la classe de modèle `complex`, consultez .  
  
## Exemple  
  
```  
// complex_comp_flt.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <float> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type double  
   complex <double> c2double ( 1.0 , 3.0 );  
   complex <float> c2float ( c2double );  
   cout << "Implicit conversion from type double to type float,"  
        << "\n gives c2float = " << c2float << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type long double  
   complex <long double> c3longdouble ( 3.0 , 4.0 );  
   complex <float> c3float ( c3longdouble );  
   cout << "Explicit conversion from type long double to type float,"  
        << "\n gives c3float = " << c3float << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3float);  
   double argc3 = arg ( c3float);  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
  **La spécification des parties initiales réelle et imaginaire,**  
 **comme type float donne c1 \= \(4,5\)**  
**La conversion implicite du type double en type float,**  
 **donne c2float \= \(1,3\)**  
**La conversion explicite du type long double en type float,**  
 **donne c3float \= \(3,4\)**  
**Le module de c3 est récupéré auprès de c3 en utilisant : abs \( c3 \) \= 5**  
**L'argument de c3 est récupéré auprès de c3 en utilisant :**  
 **arg \( c3 \) \= 0,927295 radians, c'est\-à\-dire 53,1301 degrés.**   
## Configuration requise  
 **En\-tête** : \<complex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [complexe, classe](../standard-library/complex-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)