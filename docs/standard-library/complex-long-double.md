---
title: "complex&lt;long double&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::complex<long double>"
  - "complex<long double>"
  - "std.complex<long double>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex<long double> (fonction)"
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# complex&lt;long double&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui stocke une paire ordonnée d'objets de type `long double`, le premier représentant la partie réelle d'un nombre complexe et le deuxième représentant la partie imaginaire.  
  
## Syntaxe  
  
```  
template<>  
   class complex<long double> {  
public:  
   constexpr complex(  
      long double _RealVal = 0,   
      long double _ImagVal = 0  
   );  
complex(  
      constexpr complex<long double>& _ComplexNum  
   );  
   // rest same as template class complex  
};  
```  
  
#### Paramètres  
 `_RealVal`  
 Valeur de type **long double** pour la partie réelle du nombre complexe qui est construit.  
  
 `_ImagVal`  
 Valeur de type `long double` pour la partie imaginaire du nombre complexe qui est construit.  
  
 `_ComplexNum`  
 Nombre complexe de type **double** ou **float** dont les parties réelle et imaginaire sont utilisées pour initialiser un nombre complexe de type `long double` en cours de construction.  
  
## Valeur de retour  
 Nombre complexe de type `long double`.  
  
## Notes  
 La spécialisation explicite de la classe de modèle complex en une classe complexe de type `long double` diffère de la classe de modèle uniquement dans les constructeurs qu'elle définit.  La conversion de `long double` en **float** peut être implicite, mais la conversion de **double** en `long double` doit être de type **explicit**.  L'utilisation de **explicit** exclut l'initialisation avec la conversion de type en utilisant une syntaxe d'affectation.  
  
 Pour plus d'informations sur la classe de modèle `complex`, consultez [complexe, classe](../standard-library/complex-class.md).  Pour obtenir la liste des membres de la classe de modèle `complex`, consultez .  
  
## Exemple  
  
```  
// complex_comp_ld.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <long double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 1.0 , 3.0 );  
   complex <long double> c2longdouble ( c2float );  
   cout << "Implicit conversion from type float to type long double,"  
        << "\n gives c2longdouble = " << c2longdouble << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type double  
   complex <double> c3double ( 3.0 , 4.0 );  
   complex <long double> c3longdouble ( c3double );  
   cout << "Implicit conversion from type long double to type float,"  
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
  
  **La spécification des parties initiales réelle et imaginaire,**  
 **comme type float donne c1 \= \(4,5\)**  
**La conversion implicite du type float en type long double,**  
 **donne c2longdouble \= \(1,3\)**  
**La conversion implicite du type long double en type float,**  
 **donne c3longdouble \= \(3,4\)**  
**Le module de c3 est récupéré auprès de c3 en utilisant : abs \( c3 \) \= 5**  
**L'argument de c3 est récupéré auprès de c3 en utilisant :**  
 **arg \( c3 \) \= 0,927295 radians, c'est\-à\-dire 53,1301 degrés.**   
## Configuration requise  
 **En\-tête :** \<complex\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [complexe, classe](../standard-library/complex-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)