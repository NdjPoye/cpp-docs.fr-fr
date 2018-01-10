---
title: raw_storage_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
dev_langs: C++
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd68bfc788231ddc954b1f6e8a70d63dbcf02592
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator, classe
Classe d'adaptateur fournie pour permettre aux algorithmes de stocker leurs résultats dans la mémoire non initialisée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class OutputIterator, class Type>  
class raw_storage_iterator
```  
  
#### <a name="parameters"></a>Paramètres  
 `OutputIterator`  
 Spécifie l'itérateur de sortie de l'objet stocké.  
  
 *Type*  
 Type d'objet pour lequel le stockage est alloué.  
  
## <a name="remarks"></a>Notes  
 Cette classe décrit un itérateur de sortie qui construit des objets de type **Type** dans la séquence qu’il génère. Un objet de la classe `raw_storage_iterator`\< **ForwardIterator**, **Type**> accède au stockage via un objet itérateur vers l’avant, de la classe **ForwardIterator**, que vous spécifiez quand vous construisez l’objet. Pour un objet first de la classe **ForwardIterator**, l’expression **&\*first** doit désigner le stockage non construit pour l’objet suivant (de type **Type**) dans la séquence générée.  
  
 Cette classe d'adaptateur est utilisée quand il est nécessaire de séparer l'allocation de mémoire de la construction d'objet. Le `raw_storage_iterator` peut être utilisé pour copier des objets dans le stockage non initialisé, comme la mémoire allouée à l'aide de la fonction `malloc`.  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[raw_storage_iterator](#raw_storage_iterator)|Construit un itérateur de stockage brut avec un itérateur de sortie sous-jacent spécifié.|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[element_type](#element_type)|Fournit un type qui décrit un élément à stocker dans un itérateur de stockage brut.|  
|[iter_type](#iter_type)|Fournit un type qui décrit un itérateur sous-jacent à un itérateur de stockage brut.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator*](#op_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `ii` = `x`.|  
|[operator=](#op_eq)|Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de stockage brut * `i` = `x` pour le stockage en mémoire.|  
|[operator++](#op_add_add)|Opérateurs de préincrémentation et de postincrémentation pour les itérateurs de stockage brut.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
##  <a name="element_type"></a>  raw_storage_iterator::element_type  
 Fournit un type qui décrit un élément à stocker dans un itérateur de stockage brut.  
  
```
typedef Type element_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle de classe raw_storage_iterator **Type**.  
  
##  <a name="iter_type"></a>  raw_storage_iterator::iter_type  
 Fournit un type qui décrit un itérateur sous-jacent à un itérateur de stockage brut.  
  
```
typedef ForwardIterator iter_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **ForwardIterator**.  
  
##  <a name="op_star"></a>  raw_storage_iterator::operator*  
 Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de stockage brut \* *ii* = *x*.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’itérateur de stockage brut  
  
### <a name="remarks"></a>Notes  
 Les seules conditions que doit remplir l’itérateur de stockage brut pour un **ForwardIterator** sont les suivantes : l’expression \* *ii* = *t* doit être valide et rien ne doit être spécifié sur **operator** ou `operator=`. Les opérateurs membres dans cette implémentation retournent **\*this**, ce qui permet à [operator=](#op_eq)( **constType**&) d’effectuer le stockage réel dans une expression, telle que \* *ptr* = `val`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// raw_storage_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << i << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
  
   Int &operator=(int i)   
   {  
      if (!bIsConstructed)  
         cout << "Not constructed.\n";  
      cout << "Copying " << i << endl;    
      x = i;   
      return *this;  
   };  
  
   int x;  
  
private:  
   bool bIsConstructed;  
};  
  
int main( void)   
{  
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );  
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;  
 *pInt = 5;  
   raw_storage_iterator< Int*, Int > it( pInt );  
 *it = 5;  
}  
\* Output:   
Not constructed.  
Copying 5  
Constructing 5  
*\  
```  
  
##  <a name="op_eq"></a>  raw_storage_iterator::operator=  
 Opérateur d’assignation utilisé pour implémenter l'expression d'itérateur de stockage brut \* *i* = *x* pour le stockage en mémoire.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 Valeur de l’objet de type **Type** à stocker dans la mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 L’opérateur stocke `val` dans la mémoire, puis retourne une référence à l’itérateur de stockage brut.  
  
### <a name="remarks"></a>Notes  
 Les seules conditions que doit remplir l’itérateur de stockage brut pour un **ForwardIterator** sont les suivantes  l’expression \* *ii* = *t* doit être valide et rien ne doit être spécifié sur **operator** ou `operator=`. Ces opérateurs membres retournent **\*this**.  
  
 L’opérateur d’assignation construit l’objet suivant dans la séquence de sortie à l’aide de la valeur d’itérateur stocké first, en évaluant l’expression new de positionnement **new** ( ( `void` \*)&\* **first**) **Type**( `val`).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// raw_storage_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int   
{  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << i << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   Int &operator=( int i )   
   {  
      if ( !bIsConstructed )  
         cout << "Not constructed.\n";  
      cout << "Copying " << i << endl; x = i;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( void )  
{  
   Int *pInt = ( Int* )malloc( sizeof( Int ) );  
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;  
  
 *pInt = 5;  
  
   raw_storage_iterator<Int*, Int> it( pInt );  
 *it = 5;  
}  
\* Output:   
Not constructed.  
Copying 5  
Constructing 5  
*\  
```  
  
##  <a name="op_add_add"></a>  raw_storage_iterator::operator++  
 Opérateurs de préincrémentation et de postincrémentation pour les itérateurs de stockage brut.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de stockage brut ou référence à un itérateur de stockage brut.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur tente finalement d’extraire et de stocker un objet de type **CharType** à partir du flux d’entrée associé. Le deuxième opérateur effectue une copie de l’objet, incrémente l’objet, puis retourne la copie.  
  
 Le premier opérateur de préincrémentation incrémente l’objet itérateur de sortie stocké, puis retourne **\*this**.  
  
 Le deuxième opérateur de postincrémentation effectue une copie de **\*this**, incrémente l’objet itérateur de sortie stocké et retourne la copie.  
  
 Le constructeur stocke **first** comme objet itérateur de sortie.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// raw_storage_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
int main( void )  
{  
   int *pInt = new int[5];  
   std::raw_storage_iterator<int*,int> it( pInt );  
   for ( int i = 0; i < 5; i++, it++ ) {  
 *it = 2 * i;  
};  
  
   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;  
  
   delete[] pInt;  
}  
\* Output:   
array 0 = 0  
array 1 = 2  
array 2 = 4  
array 3 = 6  
array 4 = 8  
*\  
```  
  
##  <a name="raw_storage_iterator"></a>  raw_storage_iterator::raw_storage_iterator  
 Construit un itérateur de stockage brut avec un itérateur de sortie sous-jacent spécifié.  
  
```
explicit raw_storage_iterator(ForwardIterator first);
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Itérateur vers l’avant devant être sous-jacent à l’objet `raw_storage_iterator` construit.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// raw_storage_iterator_ctor.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int  
{  
public:  
   Int(int i)  
   {  
      cout << "Constructing " << i << endl;  
      x = i;  
      bIsConstructed = true;  
   };  
   Int &operator=( int i )  
   {  
      if (!bIsConstructed)  
         cout << "Error! I'm not constructed!\n";  
      cout << "Copying " << i << endl;  x = i; return *this;  
   };  
   int x;  
   bool bIsConstructed;  
};  
  
int main( void )  
{  
   std::list<int> l;  
   l.push_back( 1 );  
   l.push_back( 2 );  
   l.push_back( 3 );  
   l.push_back( 4 );  
  
   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));  
   memset (pInt, 0, sizeof(Int)*l.size( ));  
   // Hack: make sure bIsConstructed is false  
  
   std::copy( l.begin( ), l.end( ), pInt );  // C4996  
   for (unsigned int i = 0; i < l.size( ); i++)  
      cout << "array " << i << " = " << pInt[i].x << endl;;  
  
   memset (pInt, 0, sizeof(Int)*l.size( ));  
   // hack: make sure bIsConstructed is false  
  
   std::copy( l.begin( ), l.end( ),  
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996  
   for (unsigned int i = 0; i < l.size( ); i++ )  
      cout << "array " << i << " = " << pInt[i].x << endl;  
  
   free(pInt);  
}  
\* Output:   
Error! I'm not constructed!  
Copying 1  
Error! I'm not constructed!  
Copying 2  
Error! I'm not constructed!  
Copying 3  
Error! I'm not constructed!  
Copying 4  
array 0 = 1  
array 1 = 2  
array 2 = 3  
array 3 = 4  
Constructing 1  
Constructing 2  
Constructing 3  
Constructing 4  
array 0 = 1  
array 1 = 2  
array 2 = 3  
array 3 = 4  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



