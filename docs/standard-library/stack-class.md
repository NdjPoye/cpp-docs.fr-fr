---
title: "stack, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::stack"
  - "std.stack"
  - "stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pile, stack (classe)"
  - "stack (classe)"
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# stack, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe d'adaptateur de conteneur modèle qui fournit une restriction des fonctionnalités limitant l'accès à l'élément ajouté le plus récemment pour un type de conteneur sous-jacent. La classe stack est utilisée quand il est important de s'assurer que seules des opérations de pile sont effectuées sur le conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type*  
 Type de données des éléments à stocker dans la pile.  
  
 `Container`  
 Type du conteneur sous-jacent utilisé pour implémenter la pile. La valeur par défaut est la classe `deque`*\< Type>*.  
  
## <a name="remarks"></a>Notes  
 Les éléments de classe **Type** stipulé dans le modèle de paramètre d’un objet de la pile est synonyme de [value_type](#stack__value_type) et doit correspondre au type d’élément de la classe de conteneur sous-jacent **conteneur** fixé par le deuxième paramètre du modèle. Le **Type** doit être assignable, afin qu’il soit possible de copier des objets de ce type et pour affecter des valeurs aux variables de ce type.  
  
 Incluent des classes de conteneur sous-jacent approprié pour la pile [deque](../standard-library/deque-class.md), [list, classe](../standard-library/list-class.md), et [vector, classe](vector%20Class.md), ou tout autre conteneur de séquence qui prend en charge les opérations de **dans**, `push_back`, et `pop_back`. La classe de conteneur sous-jacent est encapsulée dans l'adaptateur de conteneur, qui expose seulement l'ensemble limité de fonctions membres du conteneur de séquence comme une interface publique.  
  
 Les objets de la pile sont si comparables d’égalité et seulement si les éléments de classe **Type** égalité comparables et inférieur-que comparable si et seulement si les éléments de classe **Type** sont inférieures-que comparable.  
  
-   La classe stack prend en charge une structure de données LIFO (dernier entré, premier sorti). Une bonne analogie à avoir à l'esprit est celle d'une pile d'assiettes. Les éléments (les assiettes) peuvent être insérés, inspectés ou supprimés seulement à partir du haut de la pile, qui est le dernier élément à la fin du conteneur de base. La restriction qui fait que seul l'élément du haut est accessible est la raison de l'utilisation de la classe stack.  
  
-   Le [queue, classe](../standard-library/queue-class.md) prend en charge une structure de données premier entré, premier sorti (FIFO). Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file pour un employé de banque. Les éléments (les personnes) peuvent être ajoutés à l'arrière de la file et ils sont supprimés de l'avant de la file. Le début et la fin d'une file peuvent être inspectés. La restriction qui fait que seuls les éléments de l'avant et de l'arrière sont accessibles de cette façon est la raison de l'utilisation de la classe queue.  
  
-   Le [priority_queue (classe)](../standard-library/priority-queue-class.md) trie ses éléments afin que le plus grand élément est toujours dans la position supérieure. Elle prend en charge l'insertion d'un élément, et l'inspection et la suppression de l'élément du haut. Une bonne analogie à avoir à l'esprit est celle de personnes faisant la file, classées selon leur âge, leur taille ou un autre critère.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[pile](#stack__stack)|Construit un objet `stack` qui est vide ou qui est une copie de l'objet conteneur de base.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|Type qui fournit le conteneur de base à adapter par un objet `stack`.|  
|[size_type](#stack__size_type)|Type entier non signé qui peut représenter le nombre d'éléments dans un `stack`.|  
|[Value_type](#stack__value_type)|Type qui représente le type d'objet stocké en tant qu'élément dans un objet `stack`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[vide](#stack__empty)|Vérifie si l'objet `stack` est vide.|  
|[POP](#stack__pop)|Supprime l'élément du haut de l'objet `stack`.|  
|[push](#stack__push)|Ajoute un élément en haut de l'objet `stack`.|  
|[taille](#stack__size)|Retourne le nombre d'éléments d'un `stack`.|  
|[Retour au début](#stack__top)|Retourne une référence à un élément en haut de l'objet la`stack`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< pile>  
  
 **Espace de noms :** std  
  
##  <a name="a-namestackcontainertypea-stackcontainertype"></a><a name="stack__container_type"></a>  Stack::container_type  
 Type qui fournit le conteneur de base à adapter.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Container`. Les trois classes de conteneur de séquence STL, la classe vector, classe de liste et le deque de classe par défaut : remplissent les conditions pour être utilisé comme conteneur de base pour un objet de la pile. Répondant à ces exigences de types définis par l’utilisateur peuvent également être utilisés.  
  
 Pour plus d’informations sur `Container`, consultez la section Notes de la [stack, classe](../standard-library/stack-class.md) rubrique.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [stack::stack](#stack__stack) pour obtenir un exemple montrant comment déclarer et utiliser `container_type`.  
  
##  <a name="a-namestackemptya-stackempty"></a><a name="stack__empty"></a>  Stack::Empty  
 Vérifie si une pile est vide.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** Si la pile est vide ; **false** Si la pile n’est pas vide.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="a-namestackpopa-stackpop"></a><a name="stack__pop"></a>  Stack::POP  
 Supprime l’élément du haut de la pile.  
  
```  
void pop();
```  
  
### <a name="remarks"></a>Notes  
 La pile doit être vide pour appliquer la fonction membre. En haut de la pile est la position occupée par l’élément ajouté récemment et le dernier élément à la fin du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="a-namestackpusha-stackpush"></a><a name="stack__push"></a>  Stack::push  
 Ajoute un élément à l’extrémité supérieure de la pile.  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>Paramètres  
 ` val`  
 L’élément est ajouté en haut de la pile.  
  
### <a name="remarks"></a>Notes  
 En haut de la pile est la position occupée par l’élément ajouté récemment et le dernier élément à la fin du conteneur.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="a-namestacksizea-stacksize"></a><a name="stack__size"></a>  Stack::Size  
 Retourne le nombre d’éléments dans la pile.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur actuelle de la pile.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="a-namestacksizetypea-stacksizetype"></a><a name="stack__size_type"></a>  Stack::size_type  
 Type d’entier non signé qui peut représenter le nombre d’éléments dans une pile.  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `size_type` du conteneur base adapté par la pile.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [taille](#stack__size) pour obtenir un exemple montrant comment déclarer et utiliser `size_type`.  
  
##  <a name="a-namestackstacka-stackstack"></a><a name="stack__stack"></a>  Stack::Stack  
 Construit une pile qui est vide ou qui est une copie d’une classe de conteneur de la base.  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Le conteneur dont la pile construite doit être une copie.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="a-namestacktopa-stacktop"></a><a name="stack__top"></a>  Stack::Top  
 Retourne une référence à un élément en haut de la pile.  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence au dernier élément dans le conteneur en haut de la pile.  
  
### <a name="remarks"></a>Notes  
 La pile doit être vide pour appliquer la fonction membre. En haut de la pile est la position occupée par l’élément ajouté récemment et le dernier élément à la fin du conteneur.  
  
 Si la valeur de retour de **haut** est affecté à un `const_reference`, l’objet de pile ne peut pas être modifié. Si la valeur de retour de **haut** est affecté à un **référence**, l’objet de pile peut être modifié.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="a-namestackvaluetypea-stackvaluetype"></a><a name="stack__value_type"></a>  Stack::Value_type  
 Type qui représente le type d’objet stocké comme un élément dans une pile.  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de `value_type` du conteneur base adapté par la pile.  
  
### <a name="example"></a>Exemple  
  
```  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

