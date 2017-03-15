---
title: "&lt;valarray&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
caps.latest.revision: 8
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c2d2d523f8085db02336be1efc80f34b5cf62b27
ms.lasthandoff: 02/24/2017

---
# <a name="ltvalarraygt-operators"></a>&lt;valarray&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator&amp;](#operator_amp_)|  
|[operator&amp;&amp;](#operator_amp__amp_)|[operator&gt;](#operator_gt_)|[operator&gt;&gt;](#operator_gt__gt_)|  
|[operator&gt;=](#operator_gt__eq)|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|  
|[operator&lt;=](#operator_lt__eq)|[operator*](#operator_star)|[operator+](#operator_add)|  
|[operator-](#operator-)|[operator/](#operator_)|[operator==](#operator_eq_eq)|  
|[operator^](#operator_xor)|[operator|](#operator_or)|[operator||](#operator_lor)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Teste si les éléments correspondants de deux valarrays de taille égale sont inégaux ou si tous les éléments d’un valarray sont inégaux à une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator!=(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator!=(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator!=(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être testés pour vérifier leur inégalité.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être testés pour vérifier leur inégalité.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si les éléments correspondants sont inégaux.  
  
- **false** si les éléments correspondants ne sont pas inégaux.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur du modèle retourne un objet de classe [valarray\<bool>](../standard-library/valarray-bool-class.md), dont chaque élément `I` est ` left`[ `I`] != ` right`[ `I`].  
  
 Le deuxième opérateur du modèle stocke dans l’élément *I  left*[ `I`] != _ *Right*.  
  
 Le troisième opérateur du modèle stocke dans l’élément *I  left* != ` right`[ `I`].  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_ne.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL != vaR );  
   cout << "The element-by-element result of "  
        << "the not equal comparison test is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the not equal comparison test is the  
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-nameoperatormoda--operator"></a><a name="operator_mod"></a>  operator%  
 Obtient le reste de la division des éléments correspondants de deux valarrays de taille égale, de la division d’un valarray par une valeur spécifiée ou de la division d’une valeur spécifiée par un valarray.  
  
```  
template <class Type>  
valarray<Type>  
operator%(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator%(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator%(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Valeur ou valarray qui sert de dividende qui doit être divisé par une autre valeur ou un autre valarray.  
  
 ` right`  
 Valeur ou valarray qui sert de diviseur et qui divise une autre valeur ou un autre valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont les restes au niveau des éléments de ` left` divisé par ` right.`  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_rem.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 6 ), vaR ( 6 );  
   valarray<int> vaREM ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  53;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -67;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  3*i+1;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaREM = ( vaL % vaR );  
   cout << "The remainders from the element-by-element "  
        << "division is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaREM [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).  
The initial Right valarray is: ( 1 4 7 10 13 16 ).  
The remainders from the element-by-element division is the  
 valarray: ( 0 -3 4 -7 1 -3 ).  
*\  
```  
  
##  <a name="a-nameoperatorampa--operatoramp"></a><a name="operator_amp_"></a>  operator&amp;  
 Obtient le résultat de l’opération de bits **AND** entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d’élément.  
  
```  
template <class Type>  
valarray<Type>  
operator&(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator&(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator&(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits **AND** ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits **AND** ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont la combinaison au niveau des éléments de l’opération de bits AND de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, **longdouble**, `void``bool` ou autres.  
  
 L’opérateur de bits **AND** a la même table de vérité que l’opérateur logique **AND**, mais il s’applique au type de données au niveau des bits individuels. L’opérateur [operator&&](../standard-library/valarray-operators.md#operator_amp__amp_) s’applique au niveau d’un élément et compte toutes les valeurs différentes de zéro comme true : le résultat est un valarray de valeurs booléennes. L’opérateur de bits **ANDoperator&**, en revanche, peut fournir un valarray de valeurs autres que 0 et 1, selon le résultat de l’opération de bits.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_bitand.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<int> vaBWA ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i+1;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaBWA = ( vaL & vaR );  
   cout << "The element-by-element result of "  
        << "the bitwise operator & is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaBWA [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the bitwise operator & is the  
 valarray: ( 0 0 0 0 0 4 0 0 0 8 ).  
*\  
```  
  
##  <a name="a-nameoperatorampampa--operatorampamp"></a><a name="operator_amp__amp_"></a>  operator&amp;&amp;  
 Obtient le résultat de l’opération logique **AND** entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d’élément du valarray.  
  
```  
template <class Type>  
valarray<bool>  
operator&&(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator&&(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator&&(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur logique **AND** ou une valeur spécifiée du type d’élément qui doit être combinée avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur logique **AND** ou une valeur spécifiée du type d’élément qui doit être combinée avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont de type bool et sont la combinaison au niveau des éléments de l’opération logique **AND** de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 L’opérateur logique **ANDoperator&&** s’applique au niveau d’un élément et compte toutes les valeurs différentes de zéro comme true : le résultat est un valarray de valeurs booléennes. La version au niveau du bit de l’opérateur **AND**, [operator&,](../standard-library/valarray-operators.md#operator_amp_), en revanche, peut fournir un valarray de valeurs autres que 0 et 1, selon le résultat de l’opération de bits.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_logand.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaLAA ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaLAA = ( vaL && vaR );  
   cout << "The element-by-element result of "  
        << "the logical AND operator&& is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaLAA [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the logical AND operator&& is the  
 valarray: ( 0 0 0 1 0 1 0 1 0 1 ).  
*\  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 Teste si les éléments d’un valarray sont supérieurs aux éléments d’un valarray de taille égale ou si tous les éléments d’un valarray sont supérieurs ou inférieurs à une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator>(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator>(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator>(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si la valeur ou l’élément ` left` est supérieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
- **false** si la valeur ou l’élément ` left` n’est pas supérieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
### <a name="remarks"></a>Notes  
 Si le nombre d’éléments dans les deux valarrays n’est pas égal, le résultat est indéfini.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_gt.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i - 1;  
  
   cout << "The initial Left valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL > vaR );  
   cout << "The element-by-element result of "  
        << "the greater than comparison test is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).  
The element-by-element result of the greater than comparison test is the  
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).  
*\  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 Teste si les éléments d'un valarray sont supérieurs ou égaux aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou égaux à, ou inférieurs ou égaux à, une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator>=(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator>=(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator>=(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si la valeur ou l’élément ` left` est supérieur(e) ou égale(e) à la valeur ou l’élément ` right` correspondant(e).  
  
- **false** si la valeur ou l’élément ` left` est inférieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
### <a name="remarks"></a>Notes  
 Si le nombre d’éléments dans les deux valarrays n’est pas égal, le résultat est indéfini.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_ge.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i - 1;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL >= vaR );  
   cout << "The element-by-element result of "  
        << "the greater than or equal test is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).  
The element-by-element result of the greater than or equal test is the  
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).  
*\  
```  
  
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a>  operator&gt;&gt;  
 Décale vers la droite les bits de chaque élément d'un valarray d'un nombre spécifié de positions ou d'une quantité d'éléments spécifiée par un deuxième valarray.  
  
```  
template <class Type>  
valarray<Type>  
operator>>(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator>>(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator>>(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 La valeur à décaler ou le valarray dont les éléments doivent être décalés.  
  
 ` right`  
 La valeur qui indique la quantité de décalage vers la droite ou le valarray dont les éléments indiquent la quantité d’éléments de décalage vers la droite.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments ont été décalés vers la droite de la quantité spécifiée.  
  
### <a name="remarks"></a>Notes  
 Les signes des nombres signés sont préservés.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_rs.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   valarray<int> vaNE ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  64;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -64;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL >> vaR );  
   cout << "The element-by-element result of "  
        << "the right shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the right shift is the  
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).  
*\  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Teste si les éléments d'un valarray sont inférieurs aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou inférieurs à une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator<(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator<(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator<(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si la valeur ou l’élément ` left` est inférieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
- **false** si la valeur ou l’élément ` left` n’est pas inférieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
### <a name="remarks"></a>Notes  
 Si le nombre d’éléments dans les deux valarrays n’est pas égal, le résultat est indéfini.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_lt.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL < vaR );  
   cout << "The element-by-element result of "  
        << "the less-than comparson test is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the less-than comparson test is the  
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 Teste si les éléments d'un valarray sont inférieurs ou égaux aux éléments d'un valarray de taille égale ou si tous les éléments d'un valarray sont supérieurs ou égaux à, ou inférieurs ou égaux à, une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator<=(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator<=(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator<=(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être comparés ou une valeur spécifiée qui doit être comparée à chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si la valeur ou l’élément ` left` est inférieur(e) ou égale(e) à la valeur ou l’élément ` right` correspondant(e).  
  
- **false** si la valeur ou l’élément ` left` est supérieur(e) à la valeur ou l’élément ` right` correspondant(e).  
  
### <a name="remarks"></a>Notes  
 Si le nombre d’éléments dans les deux valarrays n’est pas égal, le résultat est indéfini.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_le.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i - 1;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL <= vaR );  
   cout << "The element-by-element result of "  
        << "the less than or equal test is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).  
The element-by-element result of the less than or equal test is the  
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 Décale vers la gauche les bits de chaque élément d'un valarray d'un nombre spécifié de positions ou d'une quantité d'éléments spécifiée par un deuxième valarray.  
  
```  
template <class Type>  
valarray<Type>  
operator<<(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator<<(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator<<(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 La valeur à décaler ou le valarray dont les éléments doivent être décalés.  
  
 ` right`  
 La valeur qui indique la quantité de décalage vers la gauche ou le valarray dont les éléments indiquent la quantité d’éléments de décalage vers la gauche.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments ont été décalés vers la gauche de la quantité spécifiée.  
  
### <a name="remarks"></a>Notes  
 Les signes des nombres signés sont préservés.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_ls.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   valarray<int> vaNE ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL << vaR );  
   cout << "The element-by-element result of "  
        << "the left shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the left shift is the  
 valarray: ( 1 -2 4 -8 16 -32 64 -128 ).  
*\  
```  
  
##  <a name="a-nameoperatorstara--operator"></a><a name="operator_star"></a>  operator*  
 Obtient le produit au niveau des éléments entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée.  
  
```  
template <class Type>  
valarray<Type>  
operator*(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator*(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator*(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être multipliés ou une valeur spécifiée qui doit être multipliée avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être multipliés ou une valeur spécifiée qui doit être multipliée avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont le produit au niveau des éléments de ` left` et ` right.`  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_eprod.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   valarray<int> vaNE ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL * vaR );  
   cout << "The element-by-element result of "  
        << "the multiplication is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the multiplication is the  
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).  
*\  
```  
  
##  <a name="a-nameoperatoradda--operator"></a><a name="operator_add"></a>  operator+  
 Obtient la somme au niveau des éléments entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée.  
  
```  
template <class Type>  
valarray<Type>  
operator+(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator+(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator+(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être ajoutés ou une valeur spécifiée qui doit être ajoutée à chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être ajoutés ou une valeur spécifiée qui doit être ajoutée à chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont la somme au niveau des éléments de ` left` et ` right.`  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_esum.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   valarray<int> vaNE ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL + vaR );  
   cout << "The element-by-element result of "  
        << "the sum is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the sum is the  
 valarray: ( 2 0 4 2 6 4 8 6 ).  
*\  
```  
  
##  <a name="a-nameoperator-a--operator-"></a><a name="operator-"></a>  operator-  
 Obtient la différence au niveau des éléments entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée.  
  
```  
template <class Type>  
valarray<Type>  
operator-(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator-(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator-(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Valeur ou valarray qui sert de diminuende auquel d’autres valeurs ou valarrays doivent être soustraits pour fournir la différence.  
  
 ` right`  
 Valeur ou valarray qui sert de diminuteur à soustraire à d’autres valeurs ou valarrays pour fournir la différence.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont la différence au niveau des éléments de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 Terminologie arithmétique utilisée pour décrire une soustraction :  
  
 différence = diminuende – diminuteur  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_ediff.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   valarray<int> vaNE ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  10;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL - vaR );  
   cout << "The element-by-element result of "  
        << "the difference is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the difference is the  
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).  
*\  
```  
  
##  <a name="a-nameoperatora--operator"></a><a name="operator_"></a>  operator/  
 Obtient le quotient au niveau des éléments entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée.  
  
```  
template <class Type>  
valarray<Type>  
operator/(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator/(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator/(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Valeur ou valarray qui sert de dividende qui doit être divisé par une autre valeur ou un autre valarray.  
  
 ` right`  
 Valeur ou valarray qui sert de diviseur et qui divise une autre valeur ou un autre valarray pour fournir le quotient.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont le quotient au niveau des éléments de ` left` divisé par ` right.`  
  
### <a name="remarks"></a>Notes  
 Terminologie arithmétique utilisée pour décrire une division :  
  
 quotient = dividende / diviseur  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_equo.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<double> vaL ( 6 ), vaR ( 6 );  
   valarray<double> vaNE ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  100;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -100;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  2*i;  
  
   cout << "The initial Left valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL / vaR );  
   cout << "The element-by-element result of "  
        << "the quotient is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).  
The initial Right valarray is: ( 0 2 4 6 8 10 ).  
The element-by-element result of the quotient is the  
 valarray: ( 1.#INF -50 25 -16.6667 12.5 -10 ).  
*\  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Teste si les éléments correspondants de deux valarrays de taille égale sont égaux ou si tous les éléments d’un valarray sont égaux à une valeur spécifiée.  
  
```  
template <class Type>  
valarray<bool>  
operator==(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator==(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator==(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments doivent être testés pour vérifier leur égalité.  
  
 ` right`  
 Le second des deux valarrays dont les éléments doivent être testés pour vérifier leur égalité.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray de valeurs booléennes, dont chacune est :  
  
- **true** si les éléments correspondants sont égaux.  
  
- **false** si les éléments correspondants ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur du modèle retourne un objet de classe [valarray\<bool>](../standard-library/valarray-bool-class.md), dont chaque élément `I` est _ *Left*[ `I`] == \_ *Right*[ `I`]. Le deuxième opérateur du modèle stocke dans l’élément `I`` left`[ `I`] == \_ *Right*. Le troisième opérateur du modèle stocke dans l’élément `I`` left` == ` right`[ `I`].  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_eq.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaNE ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNE = ( vaL == vaR );  
   cout << "The element-by-element result of "  
        << "the equality comparison test is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNE [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the equality comparison test is the  
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).  
*\  
```  
  
##  <a name="a-nameoperatorxora--operator"></a><a name="operator_xor"></a>  operator^  
 Obtient le résultat de l’opération de bits `OR` ( **XOR**) exclusive entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d’élément.  
  
```  
template <class Type>  
valarray<Type>  
operator^(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator^(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator^(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits **XOR** ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits **XOR** ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont la combinaison au niveau des éléments de l’opération de bits **XOR** de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, `long double`, `void``bool` ou autres.  
  
 L’opération de bits `OR` ( **XOR**) exclusive a la sémantique suivante : étant donné les bits *b*1 et *b*2, *b*1 **XOR** *b*2 a la valeur **true** si exactement un des bits a la valeur true ; **false** si les deux bits ont la valeur false ou si les deux bits ont la valeur true.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_xor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<int> vaLAA ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial Left valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaLAA = ( vaL ^ vaR );  
   cout << "The element-by-element result of "  
        << "the bitwise XOR operator^ is the\n valarray: ( ";  
           for ( i = 0 ; i < 10 ; i++ )  
         cout << vaLAA [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise XOR operator^ is the  
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).  
*\  
```  
  
##  <a name="a-nameoperatorora--operator124"></a><a name="operator_or"></a>  operator&#124;  
 Obtient le résultat de l'opération `OR` binaire entre des éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d'élément.  
  
```  
template <class Type>  
valarray<Type>  
operator|(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<Type>  
operator|(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<Type>  
operator|(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits `OR` ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur de bits `OR` ou une valeur spécifiée du type d’élément qui doit être combinée au niveau du bit avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont la combinaison au niveau des éléments de l’opération de bits `OR` de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 Une opération de bits peut uniquement servir à manipuler des bits dans les types de données `char` et `int`, et leurs variantes, et non pas sur des types de données plus complexes **float**, **double**, **longdouble**, `void`, `bool` ou autres.  
  
 L’opérateur de bits OR a la même table de vérité que l’opérateur logique `OR`, mais il s’applique au type de données au niveau des bits individuels. Étant donné les bits *b*1 et *b*2, *b*1 `OR` *b*2 a la valeur **true** si au moins un des bits a la valeur true ou **false** si les deux bits ont la valeur false. L’opérateur logique `OR`[operator&#124;&#124;](../standard-library/valarray-operators.md#operator_lor) s’applique au niveau d’un élément et compte toutes les valeurs différentes de zéro comme **true** : le résultat est un valarray de valeurs booléennes. L’opérateur de bits OR `operator|`, en revanche, peut fournir un valarray de valeurs autres que 0 et 1, selon le résultat de l’opération de bits.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_bitor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<int> vaLAA ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial Left valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaLAA = ( vaL | vaR );  
   cout << "The element-by-element result of "  
        << "the bitwise OR operator| is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaLAA [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise OR operator| is the  
 valarray: ( 1 0 1 3 3 4 7 6 7 9 ).  
*\  
```  
  
##  <a name="a-nameoperatorlora--operator124124"></a><a name="operator_lor"></a>  operator&#124;&#124;  
 Obtient le résultat de l’opération logique `OR` entre les éléments correspondants de deux valarrays de taille égale ou entre un valarray et une valeur spécifiée du type d’élément du valarray.  
  
```  
template <class Type>  
valarray<bool>  
operator||(
    const valarray<Type>& left,  
    const valarray<Type>& right);

template <class Type>  
valarray<bool>  
operator||(
    const valarray<Type>& left,  
    const Type& right);

template <class Type>  
valarray<bool>  
operator||(
    const Type& left,  
    const valarray<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 Le premier des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur logique `OR` ou une valeur spécifiée du type d’élément qui doit être combinée avec chaque élément d’un valarray.  
  
 ` right`  
 Le second des deux valarrays dont les éléments respectifs doivent être combinés avec l’opérateur logique `OR` ou une valeur spécifiée du type d’élément qui doit être combinée avec chaque élément d’un valarray.  
  
### <a name="return-value"></a>Valeur de retour  
 Un valarray dont les éléments sont de type `bool` et sont la combinaison au niveau des éléments de l’opération logique OR de ` left` et ` right.`  
  
### <a name="remarks"></a>Notes  
 L’opérateur logique `OR``operator||` s’applique au niveau d’un élément et compte toutes les valeurs différentes de zéro comme **true** : le résultat est un valarray de valeurs booléennes. La version au niveau du bit de l’opérateur `OR`, [operator&#124;](../standard-library/valarray-operators.md#operator_or), en revanche, peut fournir un valarray de valeurs autres que 0 et 1, selon le résultat de l’opération de bits.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// valarray_op_logor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaLOR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  0;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  0;  
  
   cout << "The initial Left valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaLOR = ( vaL || vaR );  
   cout << "The element-by-element result of "  
        << "the logical OR operator|| is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaLOR [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).  
The element-by-element result of the logical OR operator|| is the  
 valarray: ( 0 0 0 1 0 1 1 1 0 1 ).  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<valarray>](../standard-library/valarray.md)


