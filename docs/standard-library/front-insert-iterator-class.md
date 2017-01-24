---
title: "front_insert_iterator, classe | Microsoft Docs"
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
  - "iterator/std::front_insert_iterator"
  - "std::front_insert_iterator"
  - "std.front_insert_iterator"
  - "front_insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_insert_iterator (classe)"
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# front_insert_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un adaptateur d’itérateur qui répond aux exigences d’un itérateur de sortie. Elle insère, plutôt que remplace, des éléments du début d'une séquence et fournit ainsi une sémantique différente de la sémantique de remplacement fournie par les itérateurs des conteneurs de la séquence C++. La classe `front_insert_iterator` est mise en modèle d'après le type de conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Container`  
 Type de conteneur au début duquel des éléments doivent être insérés par un `front_insert_iterator`.  
  
## <a name="remarks"></a>Notes  
 Le conteneur doit répondre aux exigences d’une insertion de début de séquence où il est possible d’insérer des éléments au début de la séquence dans le temps fixe amorti. Les conteneurs de séquence STL définis par la [classe deque](../standard-library/deque-class.md) et [list, classe](../standard-library/list-class.md) fournissent les informations nécessaires `push_front` membre fonctionnent et répondent à ces exigences. En revanche, conteneurs de séquence définis par le [vector, classe](vector%20Class.md) ne répondent pas à ces exigences et ne peut pas être adapté à utiliser avec `front_insert_iterator`s. Un `front_insert_iterator` doit toujours être initialisé avec son conteneur.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|Crée un itérateur qui peut insérer des éléments au début d'un objet conteneur spécifié.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|Type qui représente le conteneur dans lequel une insertion de début doit être effectuée.|  
|[référence](#front_insert_iterator__reference)|Type qui fournit une référence à un élément dans une séquence contrôlée par le conteneur associé.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[* (opérateur)](#front_insert_iterator__operator_star)|Opérateur de suppression de référence utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de début.|  
|[operator ++](#front_insert_iterator__operator_add_add)|Incrémente le `front_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.|  
|[opérateur =](#front_insert_iterator__operator_eq)|Opérateur d’assignation utilisé pour implémenter l’expression d’itérateur de sortie * `i` = `x` pour une insertion de début.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête**: \< itérateur>  
  
 **Espace de noms :** std  
  
##  <a name="a-namefrontinsertiteratorcontainertypea-frontinsertiteratorcontainertype"></a><a name="front_insert_iterator__container_type"></a>  front_insert_iterator::container_type  
 Type qui représente le conteneur dans lequel une insertion de début doit être effectuée.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **conteneur**.  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorfrontinsertiteratora-frontinsertiteratorfrontinsertiterator"></a><a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 Crée un itérateur qui peut insérer des éléments au début d'un objet conteneur spécifié.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Cont`  
 L’objet conteneur dans lequel le `front_insert_iterator` est d’insérer des éléments.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `front_insert_iterator` pour l’objet de conteneur du paramètre.  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatorstara-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_star"></a>  front_insert_iterator::operator *  
 Déréférencer l’itérateur d’insertion renvoyer l’élément qu’il adresse.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne la valeur de l’élément traité.  
  
### <a name="remarks"></a>Notes  
 Utilisé pour implémenter l’expression d’itérateur de sortie **\*Iter** = **valeur**. Si **Iter** est un itérateur qui traite un élément dans une séquence, puis **\*Iter** = **valeur** remplace cet élément par valeur et ne modifie pas le nombre total d’éléments dans la séquence.  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoraddadda-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::operator ++  
 Incrémente le `back_insert_iterator` à l'emplacement suivant où une valeur peut être stockée.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `front_insert_iterator` traite l’emplacement suivant dans lequel une valeur peut être stockée.  
  
### <a name="remarks"></a>Notes  
 Opérateurs preincrementation et postincrementation retournent le même résultat.  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratoroperatoreqa-frontinsertiteratoroperator"></a><a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator::operator =  
 Ajoute (push) une valeur vers l’avant du conteneur.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 Valeur à affecter au conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence au dernier élément inséré au début du conteneur.  
  
### <a name="remarks"></a>Notes  
 Le premier opérateur de membre a la valeur `container.push_front( val)`, puis le renvoie `*this`.  
  
 Évalue le deuxième opérateur de membre  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 puis le renvoie `*this`.  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="a-namefrontinsertiteratorreferencea-frontinsertiteratorreference"></a><a name="front_insert_iterator__reference"></a>  front_insert_iterator::Reference  
 Type qui fournit une référence à un élément dans une séquence contrôlée par le conteneur associé.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Exemple  
  
```  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\< itérateur>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

