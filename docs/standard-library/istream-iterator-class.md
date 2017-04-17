---
title: istream_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::istream_iterator
- std.istream_iterator
- std::istream_iterator
- istream_iterator
dev_langs:
- C++
helpviewer_keywords:
- istream_iterator class
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
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
ms.openlocfilehash: e5f214501712bd8d6212f465fe82d835ccaf9028
ms.lasthandoff: 02/24/2017

---
# <a name="istreamiterator-class"></a>istream_iterator, classe
Décrit un objet itérateur d'entrée. Elle extrait des objets de classe `Type` d’un flux d’entrée, auquel elle accède par le biais d’un objet qu’elle stocke, de type `pointer` vers `basic_istream`< `CharType`, `Traits`>.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>  
class istream_iterator
 : public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`  
 Type de l'objet à extraire du flux d'entrée.  
  
 `CharType`  
 Type qui représente le type de caractère de `istream_iterator`. Cet argument est facultatif et sa valeur par défaut est `char`.  
  
 `Traits`  
 Type qui représente le type de caractère de `istream_iterator`. Cet argument est facultatif et sa valeur par défaut est `char_traits`< `CharType`>.  
  
 `Distance`  
 Type intégral signé qui représente le type de différence de `istream_iterator`. Cet argument est facultatif et sa valeur par défaut est `ptrdiff_t`.  
  
 Après avoir construit ou incrémenté un objet de classe istream_iterator avec un pointeur non null stocké, l'objet tente d'extraire et de stocker un objet de type `Type` à partir du flux d'entrée associé. Si l'extraction échoue, l'objet remplace le pointeur stocké par un pointeur null, créant ainsi un indicateur de fin de séquence.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[istream_iterator](#istream_iterator__istream_iterator)|Construit un itérateur de fin de flux comme `istream_iterator` par défaut ou un `istream_iterator` initialisé sur le type de flux de l'itérateur à partir duquel il lit.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#istream_iterator__char_type)|Type qui fournit le type de caractère de `istream_iterator`.|  
|[istream_type](#istream_iterator__istream_type)|Type qui fournit le type de flux de `istream_iterator`.|  
|[traits_type](#istream_iterator__traits_type)|Type qui fournit le type de caractéristique de `istream_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator*](#istream_iterator__operator_star)|L'opérateur de déréférencement retourne l'objet stocké de type `Type` auquel se rapporte l'objet `istream_iterator`.|  
|[operator->](#istream_iterator__operator-_gt_)|Retourne la valeur d'un membre, le cas échéant.|  
|[operator++](#istream_iterator__operator_add_add)|Extrait un objet incrémenté du flux d'entrée ou copie l'objet avant de l'incrémenter et retourne la copie.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameistreamiteratorchartypea--istreamiteratorchartype"></a><a name="istream_iterator__char_type"></a>  istream_iterator::char_type  
 Type qui fournit le type de caractère de `istream_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Chartype**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '2 4 f' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoristreamiteratora--istreamiteratoristreamiterator"></a><a name="istream_iterator__istream_iterator"></a>  istream_iterator::istream_iterator  
 Construit un itérateur de fin de flux comme `istream_iterator` par défaut ou un `istream_iterator` initialisé sur le type de flux de l'itérateur à partir duquel il lit.  
  
```
istream_iterator();

istream_iterator(istream_type& _Istr);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Istr`  
 Flux d’entrée à lire pour initialiser le `istream_iterator`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise le pointeur de flux d’entrée avec un pointeur Null et crée un itérateur de fin de flux. Le deuxième constructeur initialise le pointeur de flux d’entrée avec *&_Istr*, puis tente d’extraire et de stocker un objet de type **Type**.  
  
 Vous pouvez utiliser l’itérateur de fin de flux pour tester si un `istream_iterator` a atteint la fin d’un flux.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_istream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Used in conjunction with copy algorithm  
   // to put elements into a vector read from cin  
   vector<int> vec ( 4 );  
   vector <int>::iterator Iter;  
  
   cout << "Enter 4 integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
   istream_iterator<int> intvecRead ( cin );  
  
   // Default constructor will test equal to end of stream  
   // for delimiting source range of vecor  
   copy ( intvecRead , istream_iterator<int>( ) , vec.begin ( ) );  
   cin.clear ( );  
  
   cout << "vec = ";  
   for ( Iter = vec.begin( ) ; Iter != vec.end( ) ; Iter++ )  
      cout << *Iter << " "; cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoristreamtypea--istreamiteratoristreamtype"></a><a name="istream_iterator__istream_type"></a>  istream_iterator::istream_type  
 Type qui fournit le type de flux de `istream_iterator`.  
  
```
typedef basic_istream<CharType, Traits> istream_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `basic_istream`\< **CharType**, **Traits**>.  
  
### <a name="example"></a>Exemple  
  Pour découvrir comment déclarer et utiliser `istream_type`, consultez l’exemple relatif à [istream_iterator](#istream_iterator__istream_iterator).  
  
##  <a name="a-nameistreamiteratoroperatorstara--istreamiteratoroperator"></a><a name="istream_iterator__operator_star"></a>  istream_iterator::operator*  
 L’opérateur de déréférencement retourne l’objet stocké de type **Type** traité par `istream_iterator`.  
  
```
const Type& operator*() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet stocké de type **Type**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_operator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoroperator-gta--istreamiteratoroperator-gt"></a><a name="istream_iterator__operator-_gt_"></a>  istream_iterator::operator-&gt;  
 Retourne la valeur d'un membre, le cas échéant.  
  
```
const Type* operator->() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur d’un membre, le cas échéant.  
  
### <a name="remarks"></a>Notes  
 *i* -> équivaut à (\* *i*). *m*  
  
 L’opérateur retourne **&\*\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_operator_vm.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
#include <complex>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Enter complex numbers separated by spaces & then\n"  
        << " a character pair ( try example: '(1,2) (3,4) (a,b)' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator< complex<double> > intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<complex<double> > EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading the real part: " << intRead ->real( ) << endl;  
      cout << "Reading the imaginary part: " << intRead ->imag( ) << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoroperatoraddadda--istreamiteratoroperator"></a><a name="istream_iterator__operator_add_add"></a>  istream_iterator::operator++  
 Extrait un objet incrémenté du flux d'entrée ou copie l'objet avant de l'incrémenter et retourne la copie.  
  
```
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le premier opérateur de membre retourne une référence à l’objet incrémenté de type **Type** extrait à partir du flux d’entrée, et la deuxième fonction de membre retourne une copie de l’objet.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_operator_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratortraitstypea--istreamiteratortraitstype"></a><a name="istream_iterator__traits_type"></a>  istream_iterator::traits_type  
 Type qui fournit le type de caractéristique de `istream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **Traits**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '10 20 a' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [input_iterator_tag, struct](../standard-library/input-iterator-tag-struct.md)   
 [iterator, struct](../standard-library/iterator-struct.md)   
 [\<iterator>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)



