---
title: "queue, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.queue"
  - "std::queue"
  - "queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue (classe)"
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# queue, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de carte conteneur de modèle qui fournit une restriction de fonctionnalités pour un certain type de conteneur sous-jacent, limiter l’accès aux éléments avant et arrière. Éléments peuvent être ajoutés à l’arrière ou supprimées à l’avant, et les éléments peuvent être inspectés aux extrémités de la file d’attente.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type, class Container = deque <Type>>  
class queue  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Le type de données d’élément à stocker dans la file d’attente  
  
 `Container`  
 Le type du conteneur sous-jacent utilisé pour implémenter la file d’attente.  
  
## <a name="remarks"></a>Notes  
 Les éléments de classe **Type** stipulé dans le modèle de paramètre d’un objet de file d’attente est synonyme de [value_type](#queue__value_type) et doit correspondre au type d’élément de la classe de conteneur sous-jacent **conteneur** fixé par le deuxième paramètre du modèle. Le **Type** doit être assignable, afin qu’il soit possible de copier des objets de ce type et pour affecter des valeurs aux variables de ce type.  
  
 Incluent des classes de conteneur sous-jacent approprié pour la file d’attente [deque](../standard-library/deque-class.md) et [liste](../standard-library/list-class.md), ou tout autre conteneur de séquence qui prend en charge les opérations de `front`, **dans**, `push_back`, et `pop_front`. La classe de conteneur sous-jacent est encapsulée dans l'adaptateur de conteneur, qui expose seulement l'ensemble limité de fonctions membres du conteneur de séquence comme une interface publique.  
  
 Les objets de la file d’attente sont si comparables d’égalité et seulement si les éléments de classe **Type** égalité comparables et inférieur-que comparable si et seulement si les éléments de classe **Type** sont inférieurs-que comparable.  
  
 Il existe trois types d’adaptateurs de conteneur définis par la bibliothèque STL : priority_queue, file d’attente et pile. Chaque limite les fonctionnalités d’une classe de conteneur sous-jacent pour fournir une interface précisément contrôlée à une structure de données standard.  
  
-   Le [stack, classe](../standard-library/stack-class.md) prend en charge une structure de données dernier entré, premier sorti (LIFO). Une bonne analogie à avoir à l'esprit est celle d'une pile d'assiettes. Les éléments (les assiettes) peuvent être insérés, inspectés ou supprimés seulement à partir du haut de la pile, qui est le dernier élément à la fin du conteneur de base. La restriction qui fait que seul l'élément du haut est accessible est la raison de l'utilisation de la classe stack.  
  
-   La classe de la file d’attente prend en charge une structure de données premier entré, premier sorti (FIFO). Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file pour un employé de banque. Les éléments (les personnes) peuvent être ajoutés à l'arrière de la file et ils sont supprimés de l'avant de la file. Le début et la fin d'une file peuvent être inspectés. La restriction à l’accès aux seuls les éléments avant et arrière de cette manière est la raison de l’utilisation de la classe de la file d’attente.  
  
-   Le [priority_queue (classe)](../standard-library/priority-queue-class.md) trie ses éléments afin que le plus grand élément est toujours dans la position supérieure. Elle prend en charge l'insertion d'un élément, et l'inspection et la suppression de l'élément du haut. Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file, classées selon leur âge, leur taille ou un autre critère.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[file d’attente](#queue__queue)|Construit un objet `queue` qui est vide ou qui est une copie de l'objet conteneur de base.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#queue__container_type)|Type qui fournit le conteneur de base à adapter par le `queue`.|  
|[size_type](#queue__size_type)|Type entier non signé qui peut représenter le nombre d'éléments dans un `queue`.|  
|[Value_type](#queue__value_type)|Type qui représente le type d'objet stocké en tant qu'élément dans un objet `queue`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[Précédent](#queue__back)|Retourne une référence au dernier et plus récemment ajoutée élément dans la sauvegarde de la `queue`.|  
|[vide](#queue__empty)|Vérifie si l'objet `queue` est vide.|  
|[premier plan](#queue__front)|Retourne une référence au premier élément au début de la `queue`.|  
|[POP](#queue__pop)|Supprime un élément du début de la `queue`.|  
|[push](#queue__push)|Ajoute un élément à la fin de la `queue`.|  
|[taille](#queue__size)|Retourne le nombre d'éléments d'un `queue`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< file d’attente>  
  
 **Espace de noms :** std  
  
##  <a name="a-namequeuebacka-queueback"></a><a name="queue__back"></a>  Queue::back  
 Retourne qu'une référence au dernier et plus récemment ajoutée à l’élément à l’arrière de la file d’attente.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le dernier élément de la file d’attente. Si la file d’attente est vide, la valeur de retour est non définie.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de **retour** est affecté à un `const_reference`, l’objet de file d’attente ne peut pas être modifié. Si la valeur de retour de **retour** est affecté à un **référence**, l’objet de file d’attente peut être modifié.  
  
 Compilation avec _SECURE_SCL 1, une erreur d’exécution se produit si vous tentez d’accéder à un élément dans une file d’attente vide.  Pour plus d'informations, voir [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```  
// queue_back.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 11 );  
  
   int& i = q1.back( );  
   const int& ii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << i   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << ii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuecontainertypea-queuecontainertype"></a><a name="queue__container_type"></a>  Queue::container_type  
 Type qui fournit le conteneur de base à adapter.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Container`. Deux classes de conteneur de séquence STL, la classe de liste et la classe deque par défaut — remplissent les conditions pour être utilisé comme conteneur de base pour un objet de file d’attente. Répondant aux exigences de types définis par l’utilisateur peuvent également être utilisés.  
  
 Pour plus d’informations sur `Container`, consultez la section Notes de la [queue, classe](../standard-library/queue-class.md) rubrique.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [file d’attente](#queue__queue) pour obtenir un exemple montrant comment déclarer et utiliser `container_type`.  
  
##  <a name="a-namequeueemptya-queueempty"></a><a name="queue__empty"></a>  Queue::Empty  
 Vérifie si une file d’attente est vide.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** Si la file d’attente est vide ; **false** Si la file d’attente n’est pas vide.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_empty.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue <int> q1, q2;  
  
   q1.push( 1 );  
  
   if ( q1.empty( ) )  
      cout << "The queue q1 is empty." << endl;  
   else  
      cout << "The queue q1 is not empty." << endl;  
  
   if ( q2.empty( ) )  
      cout << "The queue q2 is empty." << endl;  
   else  
      cout << "The queue q2 is not empty." << endl;  
}  
```  
  
```Output  
The queue q1 is not empty.  
The queue q2 is empty.  
```  
  
##  <a name="a-namequeuefronta-queuefront"></a><a name="queue__front"></a>  Queue::front  
 Retourne une référence au premier élément au début de la file d’attente.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le premier élément de la file d’attente. Si la file d’attente est vide, la valeur de retour est non définie.  
  
### <a name="remarks"></a>Notes  
 Si la valeur de retour de `front` est affecté à un `const_reference`, l’objet de file d’attente ne peut pas être modifié. Si la valeur de retour de `front` est affecté à un **référence**, l’objet de file d’attente peut être modifié.  
  
 La fonction membre retourne un **référence** au premier élément de la séquence contrôlée, qui doit être non vide.  
  
 Compilation avec _SECURE_SCL 1, une erreur d’exécution se produit si vous tentez d’accéder à un élément dans une file d’attente vide.  Pour plus d'informations, voir [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Exemple  
  
```  
// queue_front.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   int& ii = q1.back( );  
   int& iii = q1.front( );  
  
   cout << "The integer at the back of queue q1 is " << ii   
        << "." << endl;  
   cout << "The integer at the front of queue q1 is " << iii   
        << "." << endl;  
}  
```  
  
##  <a name="a-namequeuepopa-queuepop"></a><a name="queue__pop"></a>  Queue::POP  
 Supprime un élément du début de la file d’attente.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Notes  
 La file d’attente doit être vide pour appliquer la fonction membre. En haut de la file d’attente est la position occupée par l’élément ajouté récemment et le dernier élément à la fin du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_pop.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, s2;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
  
   q1.pop( );  
  
   i = q1.size( );  
   cout << "After a pop the queue length is "   
        << i << "." << endl;  
  
   i = q1. front ( );  
   cout << "After a pop, the element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
After a pop the queue length is 2.  
After a pop, the element at the front of the queue is 20.  
```  
  
##  <a name="a-namequeuepusha-queuepush"></a><a name="queue__push"></a>  Queue::push  
 Ajoute un élément à la fin de la file d’attente.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 L’élément est ajouté à la fin de la file d’attente.  
  
### <a name="remarks"></a>Notes  
 L’arrière de la file d’attente est la position occupée par l’élément ajouté récemment et le dernier élément à la fin du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_push.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1;  
  
   q1.push( 10 );  
   q1.push( 20 );  
   q1.push( 30 );  
  
   queue <int>::size_type i;  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   i = q1.front( );  
   cout << "The element at the front of the queue is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 3.  
The element at the front of the queue is 10.  
```  
  
##  <a name="a-namequeuequeuea-queuequeue"></a><a name="queue__queue"></a>  Queue::Queue  
 Construit une file d’attente qui est vide ou qui est une copie d’un objet conteneur de la base.  
  
```  
queue();

explicit queue(const container_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Le **const** conteneur dont la file d’attente construit doit être une copie.  
  
### <a name="remarks"></a>Notes  
 Le conteneur de base par défaut pour la file d’attente est deque. Vous pouvez également spécifier la liste comme un conteneur de base, mais vous ne pouvez pas spécifier vecteur, car il manque requis `pop_front` fonction membre.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_queue.cpp  
// compile with: /EHsc  
#include <queue>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares queue with default deque base container  
   queue <char> q1;  
  
   // Explicitly declares a queue with deque base container  
   queue <char, deque<char> > q2;  
  
   // These lines don't cause an error, even though they  
   // declares a queue with a vector base container  
   queue <int, vector<int> > q3;  
   q3.push( 10 );  
   // but the following would cause an error because vector has   
   // no pop_front member function  
   // q3.pop( );  
  
   // Declares a queue with list base container  
   queue <int, list<int> > q4;  
  
   // The second member function copies elements from a container  
   list<int> li1;  
   li1.push_back( 1 );  
   li1.push_back( 2 );  
   queue <int, list<int> > q5( li1 );  
   cout << "The element at the front of queue q5 is "  
        << q5.front( ) << "." << endl;  
   cout << "The element at the back of queue q5 is "  
        << q5.back( ) << "." << endl;  
}  
```  
  
```Output  
The element at the front of queue q5 is 1.  
The element at the back of queue q5 is 2.  
```  
  
##  <a name="a-namequeuesizea-queuesize"></a><a name="queue__size"></a>  Queue::Size  
 Retourne le nombre d’éléments dans la file d’attente.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur actuelle de la file d’attente.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_size.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   queue <int> q1, q2;  
   queue <int>::size_type i;  
  
   q1.push( 1 );  
   i = q1.size( );  
   cout << "The queue length is " << i << "." << endl;  
  
   q1.push( 2 );  
   i = q1.size( );  
   cout << "The queue length is now " << i << "." << endl;  
}  
```  
  
```Output  
The queue length is 1.  
The queue length is now 2.  
```  
  
##  <a name="a-namequeuesizetypea-queuesizetype"></a><a name="queue__size_type"></a>  Queue::size_type  
 Type d’entier non signé qui peut représenter le nombre d’éléments dans une file d’attente.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la `size_type` du conteneur base adapté par la file d’attente.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [queue::front](#queue__front) pour obtenir un exemple montrant comment déclarer et utiliser `size_type`.  
  
##  <a name="a-namequeuevaluetypea-queuevaluetype"></a><a name="queue__value_type"></a>  Queue::Value_type  
 Type qui représente le type d’objet stocké comme un élément dans une file d’attente.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la `value_type` du conteneur base adapté par la file d’attente.  
  
### <a name="example"></a>Exemple  
  
```  
// queue_value_type.cpp  
// compile with: /EHsc  
#include <queue>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
  
   // Declares queues with default deque base container  
   queue<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   queue<int> q1;  
   q1.push(AnInt);  
   cout << "The element at the front of the queue is "  
        << q1.front( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the front of the queue is 69.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

