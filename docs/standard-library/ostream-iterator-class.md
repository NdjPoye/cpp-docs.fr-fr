---
title: ostream_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream_iterator
- std.ostream_iterator
- std::ostream_iterator
- iterator/std::ostream_iterator
dev_langs:
- C++
helpviewer_keywords:
- ostream_iterator class
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 3542d4a47abc3616c00360f9885761d08de5e884
ms.lasthandoff: 02/24/2017

---
# <a name="ostreamiterator-class"></a>ostream_iterator, classe
La classe de modèle ostream_iterator décrit un objet itérateur de sortie qui écrit les éléments consécutifs dans le flux de sortie avec l’**opérateur <<** d’extraction.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Type class CharType = char class Traits = char_traits <CharType>>  
class ostream_iterator
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Type d'objet à insérer dans le flux de sortie.  
  
 `CharType`  
 Type qui représente le type de caractère de `ostream_iterator`. Cet argument est facultatif et sa valeur par défaut est `char`*.*  
  
 `Traits`  
 Type qui représente le type de caractère de `ostream_iterator`. Cet argument est facultatif et sa valeur par défaut est `char_traits`\< *CharType>.*  
  
 La classe ostream_iterator doit répondre aux exigences d’un itérateur de sortie. Les algorithmes peuvent être enregistrés directement dans le flux de sortie à l'aide de `ostream_iterator`.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[ostream_iterator](#ostream_iterator__ostream_iterator)|Construit un `ostream_iterator` qui est initialisé et délimité en vue de son enregistrement dans le flux de sortie.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#ostream_iterator__char_type)|Type qui fournit le type de caractère de `ostream_iterator`.|  
|[ostream_type](#ostream_iterator__ostream_type)|Type qui fournit le type de flux de `ostream_iterator`.|  
|[traits_type](#ostream_iterator__traits_type)|Type qui fournit le type de caractéristique de `ostream_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator*](#ostream_iterator__operator_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x`.|  
|[operator++](#ostream_iterator__operator_add_add)|Opérateur d'incrément non fonctionnel qui retourne un `ostream_iterator` au même objet qu'il a traité avant que l'opération n'ait été appelée.|  
|[operator=](#ostream_iterator__operator_eq)|Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` en vue de l’écriture dans un flux de sortie.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameostreamiteratorchartypea--ostreamiteratorchartype"></a><a name="ostream_iterator__char_type"></a>  ostream_iterator::char_type  
 Type qui fournit le type de caractère de l’itérateur.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to the output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 10;  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
The integers written to the output stream  
by intOut are:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatorstara--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_star"></a>  ostream_iterator::operator*  
 Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie \* *ii* = *x*.  
  
```
ostream_iterator<Type, CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à `ostream_iterator`.  
  
### <a name="remarks"></a>Notes  
 La seule condition que doit remplir l’itérateur de sortie `ostream_iterator` est que l’expression \* *ii* = *t* soit valide. Il n’y a pas de condition spécifiée pour les opérateurs **operator** ou `operator=` proprement dit. L’opérateur membre dans cette implémentation retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatoraddadda--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_add_add"></a>  ostream_iterator::operator++  
 Opérateur d'incrément non fonctionnel qui retourne un `ostream_iterator` au même objet qu'il a traité avant que l'opération n'ait été appelée.  
  
```
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à `ostream_iterator`.  
  
### <a name="remarks"></a>Notes  
 Ces opérateurs membres retournent **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatoreqa--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_eq"></a>  ostream_iterator::operator=  
 Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` en vue de l’écriture dans un flux de sortie.  
  
```
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 Valeur de l’objet de type `Type` à insérer dans le flux de sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 L’opérateur insère `val` dans le flux de sortie associé à l’objet, suivi du délimiteur éventuellement spécifié dans le [constructeur ostream_iterator](#ostream_iterator__ostream_iterator), puis retourne une référence à `ostream_iterator`.  
  
### <a name="remarks"></a>Notes  
 La seule condition que doit remplir l’itérateur de sortie `ostream_iterator` est que l’expression * `ii` = `t` soit valide. Il n’y a pas de condition spécifiée pour operator ou operator= proprement dit. Cet opérateur membre retourne `*this`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratorostreamiteratora--ostreamiteratorostreamiterator"></a><a name="ostream_iterator__ostream_iterator"></a>  ostream_iterator::ostream_iterator  
 Construit un `ostream_iterator` qui est initialisé et délimité en vue de son enregistrement dans le flux de sortie.  
  
```
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Ostr`  
 Flux de sortie de type [ostream_iterator::ostream_type](#ostream_iterator__ostream_type) devant être itéré.  
  
 `_Delimiter`  
 Délimiteur qui est inséré dans le flux de sortie entre les valeurs.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise le pointeur de flux de sortie avec `&_Ostr`. Le pointeur de chaîne de délimiteur désigne une chaîne vide.  
  
 Le deuxième constructeur initialise le pointeur de flux de sortie avec `&_Ostr`, et le pointeur de chaîne de délimiteur avec `_Delimiter`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_ostream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   ostream_iterator<int> intOut ( cout , "\n" );  
 *intOut = 10;  
   intOut++;  
 *intOut = 20;  
   intOut++;  
  
   int i;  
   vector<int> vec;  
   for ( i = 1 ; i < 7 ; ++i )  
   {  
      vec.push_back (  i );  
   }  
  
   // Write elements to standard output stream  
   cout << "Elements output without delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout ) );  
   cout << endl;  
  
   // Write elements with delimiter " : " to output stream  
   cout << "Elements output with delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout, " : " ) );  
   cout << endl;  
}  
\* Output:   
10  
20  
Elements output without delimiter: 123456  
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :   
*\  
```  
  
##  <a name="a-nameostreamiteratorostreamtypea--ostreamiteratorostreamtype"></a><a name="ostream_iterator__ostream_type"></a>  ostream_iterator::ostream_type  
 Type qui fournit le type de flux de l’itérateur.  
  
```
typedef basic_ostream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, une classe stream de la hiérarchie iostream qui définit les objets pouvant être utilisés pour l’écriture.  
  
### <a name="example"></a>Exemple  
  Pour savoir comment déclarer et utiliser `ostream_type`, consultez l’exemple [ostream_iterator](#ostream_iterator__ostream_iterator).  
  
##  <a name="a-nameostreamiteratortraitstypea--ostreamiteratortraitstype"></a><a name="ostream_iterator__traits_type"></a>  ostream_iterator::traits_type  
 Type qui fournit le type des caractéristiques de caractère de l’itérateur.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Traits**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ostream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The following not OK, but are just the default values:  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 1;  
 *intOut = 10;  
 *intOut = 100;  
}  
\* Output:   
The integers written to output stream  
by intOut are:  
1  
10  
100  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




