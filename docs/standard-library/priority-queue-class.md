---
title: "priority_queue, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.priority_queue"
  - "priority_queue"
  - "std::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue (classe)"
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# priority_queue, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de carte conteneur de modèle qui fournit une restriction de la fonctionnalité de limitation de l’accès à l’élément supérieur de type conteneur sous-jacent, qui est toujours le plus grand ou de la priorité la plus élevée. Nouveaux éléments peuvent être ajoutés à la priority_queue et l’élément supérieur de la priority_queue peut être inspecté ou supprimée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>  
class priority_queue  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Type de données d’élément à stocker dans le priority_queue.  
  
 `Container`  
 Le type du conteneur sous-jacent utilisé pour implémenter le priority_queue.  
  
 *Comparer*  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d’éléments comme clés de tri pour déterminer leur ordre relatif dans le priority_queue. Cet argument est facultatif et le prédicat binaire **moins***\<***typename** *conteneur***:: value_type***>* est la valeur par défaut.  
  
## <a name="remarks"></a>Notes  
 Les éléments de classe **Type** stipulé dans le modèle de paramètre d’un objet de file d’attente est synonyme de [value_type](#priority_queue__value_type) et doit correspondre au type d’élément de la classe de conteneur sous-jacent **conteneur** fixé par le deuxième paramètre du modèle. Le **Type** doit être assignable, afin qu’il soit possible de copier des objets de ce type et pour affecter des valeurs aux variables de ce type.  
  
 Le priority_queue trie la séquence qu’elle contrôle en appelant un objet de fonction stocké de classe **caractéristiques**. En général, les éléments ne doivent pas être tout à fait comparables, afin que, à l'aide de deux événements quelconques donnés, il soit possible de déterminer, soit qu'ils soient équivalents (dans le sens où l'un n'est pas inférieur à l'autre), soit que l'un est inférieur à l'autre. Cela entraîne le tri des éléments non équivalents. D’un point de vue plus technique, la fonction de comparaison est un prédicat binaire qui induit un ordre faible strict au sens mathématique du terme.  
  
 Incluent des classes de conteneur sous-jacent adaptées pour priority_queue [deque, classe](../standard-library/deque-class.md) et la valeur par défaut [vector, classe](vector%20Class.md) ou tout autre conteneur de séquence qui prend en charge les opérations de `front`, `push_back`, et `pop_back` et un itérateur à accès aléatoire. La classe de conteneur sous-jacent est encapsulée dans l'adaptateur de conteneur, qui expose seulement l'ensemble limité de fonctions membres du conteneur de séquence comme une interface publique.  
  
 Ajout d’éléments à et suppression d’éléments dans un `priority_queue` ont tous deux la complexité logarithmique. Accès aux éléments dans un `priority_queue` a une complexité constante.  
  
 Il existe trois types d’adaptateurs de conteneur définis par la bibliothèque STL : priority_queue, file d’attente et pile. Chaque limite les fonctionnalités d’une classe de conteneur sous-jacent pour fournir une interface précisément contrôlée à une structure de données standard.  
  
-   Le [stack, classe](../standard-library/stack-class.md) prend en charge une structure de données dernier entré, premier sorti (LIFO). Une bonne analogie à avoir à l'esprit est celle d'une pile d'assiettes. Les éléments (les assiettes) peuvent être insérés, inspectés ou supprimés seulement à partir du haut de la pile, qui est le dernier élément à la fin du conteneur de base. La restriction qui fait que seul l'élément du haut est accessible est la raison de l'utilisation de la classe stack.  
  
-   Le [queue, classe](../standard-library/queue-class.md) prend en charge une structure de données premier entré, premier sorti (FIFO). Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file pour un employé de banque. Les éléments (les personnes) peuvent être ajoutés à l'arrière de la file et ils sont supprimés de l'avant de la file. Le début et la fin d'une file peuvent être inspectés. La restriction à l’accès aux seuls les éléments avant et arrière de cette manière est la raison de l’utilisation de la classe de la file d’attente.  
  
-   La classe priority_queue trie ses éléments afin que le plus grand élément est toujours dans la position supérieure. Elle prend en charge l'insertion d'un élément, et l'inspection et la suppression de l'élément du haut. Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file, classées selon leur âge, leur taille ou un autre critère.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[priority_queue](#priority_queue__priority_queue)|Construit un `priority_queue` vide ou qui est une copie d’une plage d’un objet conteneur de base ou d’autres `priority_queue`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#priority_queue__container_type)|Type qui fournit le conteneur de base à adapter par un objet `priority_queue`.|  
|[size_type](#priority_queue__size_type)|Type entier non signé qui peut représenter le nombre d'éléments dans un `priority_queue`.|  
|[Value_type](#priority_queue__value_type)|Type qui représente le type d'objet stocké en tant qu'élément dans un objet `priority_queue`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[vide](#priority_queue__empty)|Vérifie si l'objet `priority_queue` est vide.|  
|[POP](#priority_queue__pop)|Supprime l’élément le plus large de le `priority_queue` à partir de la position supérieure.|  
|[push](#priority_queue__push)|Ajoute un élément à la file d’attente de priorité en fonction de la priorité de l’élément de l’opérateur <.|  
|[taille](#priority_queue__size)|Retourne le nombre d'éléments d'un `priority_queue`.|  
|[Retour au début](#priority_queue__top)|Retourne une référence const pour le plus grand élément en haut de la `priority_queue`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< file d’attente>  
  
 **Espace de noms :** std  
  
##  <a name="a-namepriorityqueuecontainertypea-priorityqueuecontainertype"></a><a name="priority_queue__container_type"></a>  priority_queue::container_type  
 Type qui fournit le conteneur de base à adapter.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Container`. Le deque de classe de conteneur de séquence STL et le vecteur de classe par défaut remplissent les conditions pour être utilisé comme conteneur de base pour un objet priority_queue. Répondant aux exigences de types définis par l’utilisateur peuvent également être utilisés.  
  
 Pour plus d’informations sur `Container`, consultez la section Notes de la [priority_queue, classe](../standard-library/priority-queue-class.md) rubrique.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [priority_queue](#priority_queue__priority_queue) pour obtenir un exemple montrant comment déclarer et utiliser `container_type`.  
  
##  <a name="a-namepriorityqueueemptya-priorityqueueempty"></a><a name="priority_queue__empty"></a>  priority_queue::Empty  
 Teste si un priority_queue est vide.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** Si le priority_queue est vide ; **false** Si le priority_queue n’est pas vide.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue <int> q1, s2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The priority_queue q1 is empty." << endl;  
   else  
      cout << "The priority_queue q1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The priority_queue s2 is empty." << endl;  
   else  
      cout << "The priority_queue s2 is not empty." << endl;  
}  
```  
  
```Output  
The priority_queue q1 is not empty.  
The priority_queue s2 is empty.  
```  
  
##  <a name="a-namepriorityqueuepopa-priorityqueuepop"></a><a name="priority_queue__pop"></a>  priority_queue::POP  
 Supprime le plus grand élément de la priority_queue la position supérieure.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Notes  
 La file d'attente priority_queue ne doit pas être vide pour appliquer la fonction membre. En haut de la priority_queue est toujours occupé par le plus grand élément du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   priority_queue <int>::size_type i, iii;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
  
   q1.pop( );  
  
   iii = q1.size( );  
   cout << "After a pop, the priority_queue length is "   
        << iii << "." << endl;  
  
   const int& iv = q1.top( );  
   cout << "After a pop, the element at the top of the "  
        << "priority_queue is " << iv << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
After a pop, the priority_queue length is 2.  
After a pop, the element at the top of the priority_queue is 20.  
```  
  
##  <a name="a-namepriorityqueuepriorityqueuea-priorityqueuepriorityqueue"></a><a name="priority_queue__priority_queue"></a>  priority_queue::priority_queue  
 Construit un priority_queue vide ou qui est une copie d’une plage d’un objet conteneur de base ou d’un autre priority_queue.  
  
```  
priority_queue();

explicit priority_queue(const Traits&_comp);

priority_queue(const Traits&_comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp);

template <class InputIterator>  
priority_queue(InputIterator first, InputIterator last, const Traits&_comp, const container_type& _Cont);
```  
  
### <a name="parameters"></a>Paramètres  
 *_ comp*  
 La fonction de comparaison de type **constTraits** utilisée pour classer les éléments dans le priority_queue pour comparer la fonction du conteneur de base par défaut.  
  
 `_Cont`  
 Le conteneur de base dont le priority_queue construit doit être une copie.  
  
 ` right`  
 Le priority_queue dont le jeu construit doit être une copie.  
  
 ` first`  
 Position du premier élément de la plage d'éléments à copier.  
  
 ` last`  
 Position du premier élément au-delà de la plage d'éléments à copier.  
  
### <a name="remarks"></a>Notes  
 Chacun des trois premiers constructeurs spécifie un priority_queue initiale vide, la seconde spécifiez également le type de fonction de comparaison ( ` comp`) à utiliser pour établir l’ordre des éléments et le troisième spécifiant explicitement le `container_type` ( `_Cont`) à utiliser. Le mot clé **explicite** supprime certains types de conversion de type automatique.  
  
 Le quatrième constructeur spécifie une copie de la priority_queue ` right`.  
  
 Les trois dernières constructeurs copient la plage [ * first, last,*) d’un conteneur et les valeurs utilisées pour initialiser un priority_queue augmentant caractère explicite en spécifiant le type de fonction de comparaison de la classe **caractéristiques** et `container_type`.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_ctor.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <deque>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function declares priority_queue  
   // with a default vector base container  
   priority_queue <int> q1;  
   cout << "q1 = ( ";  
   while ( !q1.empty( ) )  
   {  
      cout << q1.top( ) << " ";  
      q1.pop( );  
   }  
   cout << ")" << endl;  
  
   // Explicitly declares a priority_queue with nondefault  
   // deque base container  
   priority_queue <int, deque <int> > q2;  
   q2.push( 5 );  
   q2.push( 15 );  
   q2.push( 10 );  
   cout << "q2 = ( ";  
   while ( !q2.empty( ) )  
   {  
      cout << q2.top( ) << " ";  
      q2.pop( );  
   }  
   cout << ")" << endl;  
  
   // This method of printing out the elements of a priority_queue  
   // removes the elements from the priority queue, leaving it empty  
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;  
  
   // The third member function declares a priority_queue   
   // with a vector base container and specifies that the comparison   
   // function greater is to be used for ordering elements  
   priority_queue <int, vector<int>, greater<int> > q3;  
   q3.push( 2 );  
   q3.push( 1 );  
   q3.push( 3 );  
   cout << "q3 = ( ";  
   while ( !q3.empty( ) )  
   {  
      cout << q3.top( ) << " ";  
      q3.pop( );  
   }  
   cout << ")" << endl;  
  
   // The fourth member function declares a priority_queue and  
   // initializes it with elements copied from another container:  
   // first, inserting elements into q1, then copying q1 elements into q4  
   q1.push( 100 );  
   q1.push( 200 );  
   priority_queue <int> q4( q1 );  
   cout << "q4 = ( ";     
   while ( !q4.empty( ) )  
   {  
      cout << q4.top( ) << " ";  
      q4.pop( );  
   }  
   cout << ")" << endl;  
  
   // Creates an auxiliary vector object v5 to be used to initialize q5  
   vector <int> v5;  
   vector <int>::iterator v5_Iter;  
   v5.push_back( 10 );  
   v5.push_back( 30 );  
   v5.push_back( 20 );  
   cout << "v5 = ( " ;  
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )  
      cout << *v5_Iter << " ";  
   cout << ")" << endl;  
  
   // The fifth member function declares and  
   // initializes a priority_queue q5 by copying the  
   // range v5[ first,  last) from vector v5  
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q5 = ( ";  
   while ( !q5.empty( ) )  
   {  
      cout << q5.top( ) << " ";  
      q5.pop( );  
   }  
   cout << ")" << endl;  
  
   // The sixth member function declares a priority_queue q6  
   // with a comparison function greater and initializes q6  
   // by copying the range v5[ first,  last) from vector v5  
   priority_queue <int, vector<int>, greater<int> >   
      q6( v5.begin( ), v5.begin( ) + 2 );  
   cout << "q6 = ( ";  
   while ( !q6.empty( ) )  
   {  
      cout << q6.top( ) << " ";  
      q6.pop( );  
   }  
   cout << ")" << endl;  
}  
```  
  
##  <a name="a-namepriorityqueuepusha-priorityqueuepush"></a><a name="priority_queue__push"></a>  priority_queue::push  
 Ajoute un élément à la file d’attente de priorité en fonction de la priorité de l’élément de l’opérateur <.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 L’élément est ajouté en haut de la priority_queue.  
  
### <a name="remarks"></a>Notes  
 En haut de la priority_queue est la position occupée par le plus grand élément du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuesizea-priorityqueuesize"></a><a name="priority_queue__size"></a>  priority_queue::Size  
 Retourne le nombre d’éléments dans le priority_queue.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur actuelle de la priority_queue.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue <int> q1, q2;  
   priority_queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The priority_queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 1.  
The priority_queue length is now 2.  
```  
  
##  <a name="a-namepriorityqueuesizetypea-priorityqueuesizetype"></a><a name="priority_queue__size_type"></a>  priority_queue::size_type  
 Type d’entier non signé qui peut représenter le nombre d’éléments dans un priority_queue.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la `size_type` du conteneur base adapté par le priority_queue.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [taille](#priority_queue__size) pour obtenir un exemple montrant comment déclarer et utiliser `size_type`.  
  
##  <a name="a-namepriorityqueuetopa-priorityqueuetop"></a><a name="priority_queue__top"></a>  priority_queue::Top  
 Retourne une référence à l'élément le plus grand en haut de la file d'attente priority_queue.  
  
```  
const_reference top() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’élément plus grand, comme déterminé par la **caractéristiques** (fonction), l’objet de la priority_queue.  
  
### <a name="remarks"></a>Notes  
 La file d'attente priority_queue ne doit pas être vide pour appliquer la fonction membre.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_top.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   priority_queue<int> q1;  
  
   q1.push( 10 );  
   q1.push( 30 );  
   q1.push( 20 );  
  
   priority_queue<int>::size_type i;  
   i = q1.size( );  
   cout << "The priority_queue length is " << i << "." << endl;  
  
   const int& ii = q1.top( );  
   cout << "The element at the top of the priority_queue is "  
        << ii << "." << endl;  
}  
```  
  
```Output  
The priority_queue length is 3.  
The element at the top of the priority_queue is 30.  
```  
  
##  <a name="a-namepriorityqueuevaluetypea-priorityqueuevaluetype"></a><a name="priority_queue__value_type"></a>  priority_queue::Value_type  
 Type qui représente le type d’objet stocké comme un élément dans un priority_queue.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la `value_type` du conteneur base adapté par le priority_queue.  
  
### <a name="example"></a>Exemple  
  
```  
// pqueue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares priority_queues with default deque base container  
   priority_queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   priority_queue<int> q1;  
   q1.push( AnInt );  
   cout << "The element at the top of the priority_queue is "  
        << q1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the priority_queue is 69.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

