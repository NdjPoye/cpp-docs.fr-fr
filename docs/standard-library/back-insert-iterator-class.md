---
title: "back_insert_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::back_insert_iterator"
  - "std::back_insert_iterator"
  - "back_insert_iterator"
  - "std.back_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_insert_iterator (classe)"
ms.assetid: a1ee07f2-cf9f-46a1-8608-cfaf207f9713
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# back_insert_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un adaptateur d’itérateur qui répond aux exigences d’un itérateur de sortie. Elle insère, plutôt que remplace, des éléments de la fin d'une séquence et fournit ainsi une sémantique différente de la sémantique de remplacement fournie par les itérateurs des conteneurs de la séquence C++. La classe `back_insert_iterator` est mise en modèle d'après le type de conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Container>  
class back_insert_iterator;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Container`  
 Type de conteneur à la fin duquel des éléments doivent être insérés par un `back_insert_iterator`.  
  
## <a name="remarks"></a>Notes  
 Le conteneur doit répondre aux exigences d’une insertion de fin de séquence où il est possible d’insérer des éléments à la fin de la séquence dans le temps fixe amorti. Les conteneurs de séquence STL définis par la [classe deque](../standard-library/deque-class.md), [list, classe](../standard-library/list-class.md) et [vector, classe](vector%20Class.md) fournissent les informations nécessaires `push_back` membre fonctionnent et répondent à ces exigences. Ces trois conteneurs, ainsi que les chaînes, peuvent être adaptés pour être utilisés avec des `back_insert_iterator`. Un `back_insert_iterator` doit toujours être initialisé avec son conteneur.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[back_insert_iterator](#back_insert_iterator__back_insert_iterator)|Construit `back_insert_iterator` qui insère des éléments après le dernier élément d'un conteneur.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#back_insert_iterator__container_type)|Type qui fournit un conteneur pour le `back_insert_iterator`.|  
|[référence](#back_insert_iterator__reference)|Type qui fournit une référence pour le `back_insert_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[* (opérateur)](#back_insert_iterator__operator_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de fin.|  
|[operator ++](#back_insert_iterator__operator_add_add)|Incrémente le `back_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.|  
|[opérateur =](#back_insert_iterator__operator_eq)|Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de fin.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête**: \< itérateur>  
  
 **Espace de noms :** std  
  
##  <a name="a-namebackinsertiteratorbackinsertiteratora-backinsertiteratorbackinsertiterator"></a><a name="back_insert_iterator__back_insert_iterator"></a>  back_insert_iterator::back_insert_iterator  
 Construit `back_insert_iterator` qui insère des éléments après le dernier élément d'un conteneur.  
  
```  
 
explicit back_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Cont`  
 Le conteneur qui le `back_insert_iterator` consiste à insérer un élément dans.  
  
### <a name="return-value"></a>Valeur de retour  
 A `back_insert_iterator` pour le conteneur de paramètre.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_back_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for ( i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The initial vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   // Insertions with member function  
   back_inserter ( vec ) = 40;  
   back_inserter ( vec ) = 50;  
  
   // Alternatively, insertions can be done with template function  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 600;  
   backiter++;  
 *backiter = 700;  
  
   cout << "After the insertions, the vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The initial vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec is: ( 1 2 3 40 50 600 700 ).  
```  
  
##  <a name="a-namebackinsertiteratorcontainertypea-backinsertiteratorcontainertype"></a><a name="back_insert_iterator__container_type"></a>  back_insert_iterator::container_type  
 Type qui fournit un conteneur pour le `back_insert_iterator`.  
  
```  
 
typedef Container  
container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **conteneur**.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The original vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::container_type vec1 = vec;  
   back_inserter ( vec1 ) = 40;  
  
   cout << "After the insertion, the vector is: ( ";  
   for ( vIter = vec1.begin ( ) ; vIter != vec1.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector vec is: ( 1 2 3 ).  
After the insertion, the vector is: ( 1 2 3 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatorstara-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_star"></a>  back_insert_iterator::operator *  
 Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie \* *i* = *x*.  
  
```  
back_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’élément inséré à la fin du conteneur.  
  
### <a name="remarks"></a>Notes  
 Utilisé pour implémenter l’expression d’itérateur de sortie **\*Iter** = **valeur**. Si **Iter** est un itérateur qui traite un élément dans une séquence, puis **\*Iter** = **valeur** remplace cet élément par valeur et ne modifie pas le nombre total d’éléments dans la séquence.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_back_insert.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
After the insertions, the vector vec becomes: ( 1 2 3 10 20 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoraddadda-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_add_add"></a>  back_insert_iterator::operator ++  
 Incrémente le `back_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.  
  
```  
back_insert_iterator<Container>& operator++();

back_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `back_insert_iterator` traite l’emplacement suivant dans lequel une valeur peut être stockée.  
  
### <a name="remarks"></a>Notes  
 Opérateurs preincrementation et postincrementation retournent le même résultat.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 3 ; ++i )    
   {  
      vec.push_back ( 10 * i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 30;  
   backiter++;      // Increment to the next element  
 *backiter = 40;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 10 20 ).  
After the insertions, the vector vec becomes: ( 10 20 30 40 ).  
```  
  
##  <a name="a-namebackinsertiteratoroperatoreqa-backinsertiteratoroperator"></a><a name="back_insert_iterator__operator_eq"></a>  back_insert_iterator::operator =  
 Ajoute ou exécute un push d’une valeur à la fin d’un conteneur.  
  
```  
back_insert_iterator<Container>& operator=(typename Container::const_reference val);

    back_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 La valeur à insérer dans le conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence au dernier élément inséré à la fin du conteneur.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur de membre a la valeur `Container.push_back( val)`,  
  
 puis le renvoie `*this`. Évalue le deuxième opérateur de membre  
  
 `container->push_back((typename Container::value_type&&)val)`,  
  
 puis le renvoie `*this`.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> > backiter ( vec );  
 *backiter = 10;  
   backiter++;      // Increment to the next element  
 *backiter = 20;  
   backiter++;  
  
   cout << "After the insertions, the vector vec becomes: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
##  <a name="a-namebackinsertiteratorreferencea-backinsertiteratorreference"></a><a name="back_insert_iterator__reference"></a>  back_insert_iterator::Reference  
 Type qui fournit une référence pour le `back_insert_iterator`.  
  
```  
 
typedef typename Container::reference reference;  
```  
  
### <a name="remarks"></a>Notes  
 Ce type décrit une référence à un élément de la séquence contrôlée par le conteneur associé.  
  
### <a name="example"></a>Exemple  
  
```  
// back_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      vec.push_back ( i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is: ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   back_insert_iterator<vector<int> >::reference   
        RefLast = *(vec.end ( ) - 1 );  
   cout << "The last element in the vector vec is: "   
        << RefLast << "." << endl;  
}  
```  
  
```Output  
The vector vec is: ( 1 2 3 ).  
The last element in the vector vec is: 3.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\< itérateur>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

