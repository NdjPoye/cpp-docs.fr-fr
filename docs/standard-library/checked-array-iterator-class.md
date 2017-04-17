---
title: checked_array_iterator, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/checked_array_iterator
- checked_array_iterator
- std::checked_array_iterator
- std.checked_array_iterator
dev_langs:
- C++
helpviewer_keywords:
- checked_array_iterator, syntax
- checked_array_iterator class
- checked_array_iterator
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8494fc5f7f184505bf71712d41ac290f876c1311
ms.lasthandoff: 02/24/2017

---
# <a name="checkedarrayiterator-class"></a>checked_array_iterator, classe
La classe `checked_array_iterator` vous permet de transformer un tableau ou un pointeur en un itérateur vérifié. Utilisez cette classe comme wrapper (à l’aide de la fonction [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)) pour les pointeurs ou tableaux bruts comme un moyen ciblé d’exécuter des vérifications et de gérer les avertissements de pointeur non vérifié, au lieu de désactiver globalement ces avertissements. Si nécessaire, utilisez la version non vérifiée de cette classe, [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md).  
  
> [!NOTE]
>  Cette classe est une extension Microsoft de la bibliothèque C++ Standard. Le code implémenté à l’aide de cette fonction ne peut pas être utilisé dans les environnements de build C++ standard qui ne prennent pas en charge cette extension Microsoft. Pour savoir comment écrire du code qui ne requiert pas l'utilisation de cette classe, consultez le deuxième exemple ci-dessous.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class _Iterator>  
class checked_array_iterator;
```  
  
## <a name="remarks"></a>Notes  
 Cette classe est définie dans l’espace de noms [stdext](../standard-library/stdext-namespace.md).  
  
 Pour plus d’informations et pour obtenir un exemple de code sur la fonctionnalité d’itérateur vérifié, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant indique comment définir et utiliser un itérateur vérifié de tableau.  
  
 Si la destination n'est pas suffisamment grande pour contenir tous les éléments copiés, ce qui serait le cas si vous aviez modifié la ligne suivante :  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```  
  
 à  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));
```  
  
 Une erreur d'exécution se produira.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
\* Output:   
( 0 1 2 3 4 )  
( 0 1 2 3 4 )  
*\  
```  
  
## <a name="example"></a>Exemple  
 Pour ne pas avoir besoin de la classe `checked_array_iterator` quand vous utilisez des algorithmes de bibliothèque C++ Standard, utilisez un `vector` au lieu d’un tableau alloué dynamiquement. L'exemple suivant illustre la procédure à suivre pour réaliser cette opération.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
\* Output:   
 0 1 2 3 4 5 6 7 8 9  
*\  
```  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[checked_array_iterator](#checked_array_iterator__checked_array_iterator)|Construit un `checked_array_iterator` par défaut ou un `checked_array_iterator` à partir d'un itérateur sous-jacent.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[difference_type](#checked_array_iterator__difference_type)|Type qui fournit la différence entre deux objets `checked_array_iterator` se rapportant à des éléments dans le même conteneur.|  
|[pointer](#checked_array_iterator__pointer)|Type qui fournit un pointeur vers un élément traité par un `checked_array_iterator`.|  
|[reference](#checked_array_iterator__reference)|Type qui fournit une référence à un élément traité par un `checked_array_iterator`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[base](#checked_array_iterator__base)|Récupère l'itérateur sous-jacent à partir de son `checked_array_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](#checked_array_iterator__operator_eq_eq)|Vérifie si deux objets `checked_array_iterator` sont égaux.|  
|[operator!=](#checked_array_iterator__operator_neq)|Vérifie si deux objets `checked_array_iterator` sont inégaux.|  
|[operator<](#checked_array_iterator__operator_lt_)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur au `checked_array_iterator` du côté droit.|  
|[operator>](#checked_array_iterator__operator_gt_)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur à l'objet `checked_array_iterator` du côté droit.|  
|[operator<=](#checked_array_iterator__operator_lt__eq)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur ou égal au `checked_array_iterator` du côté droit.|  
|[operator>=](#checked_array_iterator__operator_gt__eq)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur ou égal au `checked_array_iterator` du côté droit.|  
|[operator*](#checked_array_iterator__operator_star)|Retourne l'élément traité par `checked_array_iterator`.|  
|[operator->](#checked_array_iterator__operator-_gt_)|Retourne un pointeur vers l'élément traité par le `checked_array_iterator`.|  
|[operator++](#checked_array_iterator__operator_add_add)|Incrémente le `checked_array_iterator` à l'élément suivant.|  
|[operator--](#checked_array_iterator__operator--)|Décrémente le `checked_array_iterator` à l'élément précédent.|  
|[operator+=](#checked_array_iterator__operator_add_eq)|Ajoute un décalage spécifié à un `checked_array_iterator`.|  
|[operator+](#checked_array_iterator__operator_add)|Ajoute un décalage à un itérateur et retourne le nouvel `checked_array_iterator` qui se rapporte à l'élément inséré à la nouvelle position décalée.|  
|[operator-=](#checked_array_iterator__operator-_eq)|Décrémente un décalage spécifié d'un `checked_array_iterator`.|  
|[operator-](#checked_array_iterator__operator-)|Décrémente un décalage depuis un itérateur et retourne le nouveau `checked_array_iterator` qui traite l'élément inséré à la nouvelle position décalée.|  
|[operator&#91;&#93;](#checked_array_iterator__operator_at)|Retourne une référence à un élément décalé d'un nombre donné de positions par rapport à l'élément auquel un `checked_array_iterator` se rapportait.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** stdext  
  
##  <a name="a-namecheckedarrayiteratorbasea--checkedarrayiteratorbase"></a><a name="checked_array_iterator__base"></a>  checked_array_iterator::base  
 Récupère l'itérateur sous-jacent à partir de son `checked_array_iterator`.  
  
```
_Iterator base() const;
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;  
  
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   int* bpos;  
  
   stdext::checked_array_iterator<int*> rpos(V1, 10);  
   rpos++;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
\* Output:   
The iterator underlying rpos is bpos & it points to: 1.  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratorcheckedarrayiteratora--checkedarrayiteratorcheckedarrayiterator"></a><a name="checked_array_iterator__checked_array_iterator"></a>  checked_array_iterator::checked_array_iterator  
 Construit un `checked_array_iterator` par défaut ou un `checked_array _iterator` à partir d'un itérateur sous-jacent.  
  
```
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptr`  
 Pointeur vers le tableau.  
  
 `size`  
 Taille du tableau.  
  
 `index`  
 (Facultatif) Un élément du tableau, pour initialiser l’itérateur.  Par défaut, l’itérateur est initialisé au niveau du premier élément du tableau.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_ctor.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   copy (a, a + 5, checked_output_iterator);  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator2(b,5,3);  
   cout << *checked_output_iterator2 << endl;  
}  
\* Output:   
0 1 2 3 4   
0 1 2 3 4   
3  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratordifferencetypea--checkedarrayiteratordifferencetype"></a><a name="checked_array_iterator__difference_type"></a>  checked_array_iterator::difference_type  
 Type qui fournit la différence entre deux objets `checked_array_iterator` se rapportant à des éléments dans le même conteneur.  
  
```
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type de différence entre objets `checked_array_iterator` est le même que le type de différence entre itérateurs.  
  
 Consultez [checked_array_iterator::operator[]](#checked_array_iterator__operator_at) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratoroperatoreqeqa--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_eq_eq"></a>  checked_array_iterator::operator==  
 Vérifie si deux objets `checked_array_iterator` sont égaux.  
  
```
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` par rapport auquel vérifier l’égalité.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_opeq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatorneqa--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_neq"></a>  checked_array_iterator::operator!=  
 Vérifie si deux objets `checked_array_iterator` sont inégaux.  
  
```
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` par rapport auquel vérifier l’inégalité.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_opneq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatorlta--checkedarrayiteratoroperatorlt"></a><a name="checked_array_iterator__operator_lt_"></a>  checked_array_iterator::operator&lt;  
 Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur au `checked_array_iterator` du côté droit.  
  
```
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` par rapport auquel vérifier l’inégalité.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_oplt.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is not less than checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatorgta--checkedarrayiteratoroperatorgt"></a><a name="checked_array_iterator__operator_gt_"></a>  checked_array_iterator::operator&gt;  
 Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur à l'objet `checked_array_iterator` du côté droit.  
  
```
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` avec lequel effectuer la comparaison.  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::operator&lt;](#checked_array_iterator__operator_lt_) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratoroperatorlteqa--checkedarrayiteratoroperatorlt"></a><a name="checked_array_iterator__operator_lt__eq"></a>  checked_array_iterator::operator&lt;=  
 Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur ou égal au `checked_array_iterator` du côté droit.  
  
```
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` avec lequel effectuer la comparaison.  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::operator&gt;=](#checked_array_iterator__operator_gt__eq) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratoroperatorgteqa--checkedarrayiteratoroperatorgt"></a><a name="checked_array_iterator__operator_gt__eq"></a>  checked_array_iterator::operator&gt;=  
 Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur ou égal au `checked_array_iterator` du côté droit.  
  
```
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 `checked_array_iterator` avec lequel effectuer la comparaison.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_opgteq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is greater than or equal to checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatorstara--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_star"></a>  checked_array_iterator::operator*  
 Retourne l'élément traité par `checked_array_iterator`.  
  
```
reference operator*() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de l’élément ciblé par le `checked_array_iterator`.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   pair<int, int> c[1];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << endl;  
  
    c[0].first = 10;  
    c[0].second = 20;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*>::pointer p = &(*checked_output_iterator);  
   checked_array_iterator<pair<int, int>*> chk_c(c, 1);  
   checked_array_iterator<pair<int, int>*>::pointer p_c = &(*chk_c);  
  
   cout << "b[0] = " << *p << endl;  
   cout << "c[0].first = " << p_c->first << endl;  
}  
\* Output:   
0  
1  
2  
3  
4  
b[0] = 0  
c[0].first = 10  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperator-gta--checkedarrayiteratoroperator-gt"></a><a name="checked_array_iterator__operator-_gt_"></a>  checked_array_iterator::operator-&gt;  
 Retourne un pointeur vers l'élément traité par le `checked_array_iterator`.  
  
```
pointer operator->() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément ciblé par le `checked_array_iterator`.  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::pointer](#checked_array_iterator__pointer) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratoroperatoraddadda--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_add_add"></a>  checked_array_iterator::operator++  
 Incrémente le `checked_array_iterator` à l'élément suivant.  
  
```
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le premier opérateur retourne le `checked_array_iterator` préincrémenté et le deuxième, l’opérateur de postincrémentation, retourne une copie du `checked_array_iterator` incrémenté.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_plus_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   ++checked_output_iterator;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
77  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperator--a--checkedarrayiteratoroperator--"></a><a name="checked_array_iterator__operator--"></a>  checked_array_iterator::operator--  
 Décrémente le `checked_array_iterator` à l'élément précédent.  
  
```
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le premier opérateur retourne le `checked_array_iterator` prédécrémenté et le deuxième, l’opérateur de postdécrémentation, retourne une copie du `checked_array_iterator` décrémenté.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_minus_minus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator--;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
6  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatoraddeqa--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_add_eq"></a>  checked_array_iterator::operator+=  
 Ajoute un décalage spécifié à un `checked_array_iterator`.  
  
```
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage d’incrémentation de l’itérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence vers l’élément ciblé par le `checked_array_iterator`.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_plus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperatoradda--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_add"></a>  checked_array_iterator::operator+  
 Ajoute un décalage à un itérateur et retourne le nouvel `checked_array_iterator` qui se rapporte à l'élément inséré à la nouvelle position décalée.  
  
```
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage à ajouter à `checked_array_iterator`.  
  
### <a name="return-value"></a>Valeur de retour  
 `checked_array_iterator` se rapportant à l’élément de décalage.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator = checked_output_iterator + 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperator-eqa--checkedarrayiteratoroperator-"></a><a name="checked_array_iterator__operator-_eq"></a>  checked_array_iterator::operator-=  
 Décrémente un décalage spécifié d'un `checked_array_iterator`.  
  
```
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage d’incrémentation de l’itérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence vers l’élément ciblé par le `checked_array_iterator`.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_minus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator -= 2;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
199  
3  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratoroperator-a--checkedarrayiteratoroperator-"></a><a name="checked_array_iterator__operator-"></a>  checked_array_iterator::operator-  
 Décrémente un décalage depuis un itérateur et retourne le nouveau `checked_array_iterator` qui traite l'élément inséré à la nouvelle position décalée.  
  
```
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage à décrémenter du `checked_array_iterator`.  
  
### <a name="return-value"></a>Valeur de retour  
 `checked_array_iterator` se rapportant à l’élément de décalage.  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::operator-](#checked_array_iterator__operator-) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratoroperatorata--checkedarrayiteratoroperator"></a><a name="checked_array_iterator__operator_at"></a>  checked_array_iterator::operator[]  
 Retourne une référence à un élément décalé d'un nombre donné de positions par rapport à l'élément auquel un `checked_array_iterator` se rapportait.  
  
```
reference operator[](difference_type _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage par rapport au `checked_array_iterator` traité.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence au décalage de l’élément.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// checked_array_iterators_op_diff.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   // Declare a difference type for a parameter  
   stdext::checked_array_iterator<int*>::difference_type diff = 2;  
  
   stdext::checked_array_iterator<int*> VChkIter(V1, 10);  
  
   stdext::checked_array_iterator<int*>::reference refrpos = VChkIter [diff];  
  
   cout << refrpos + 1 << endl;  
}  
\* Output:   
3  
*\  
```  
  
##  <a name="a-namecheckedarrayiteratorpointera--checkedarrayiteratorpointer"></a><a name="checked_array_iterator__pointer"></a>  checked_array_iterator::pointer  
 Type qui fournit un pointeur vers un élément traité par un `checked_array_iterator`.  
  
```
typedef typename iterator_traits<_Iterator>::pointer pointer;
```  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::operator*](#checked_array_iterator__operator_star) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
##  <a name="a-namecheckedarrayiteratorreferencea--checkedarrayiteratorreference"></a><a name="checked_array_iterator__reference"></a>  checked_array_iterator::reference  
 Type qui fournit une référence à un élément traité par un `checked_array_iterator`.  
  
```
typedef typename iterator_traits<_Iterator>::reference reference;
```  
  
### <a name="remarks"></a>Notes  
 Consultez [checked_array_iterator::operator[]](#checked_array_iterator__operator_at) pour obtenir un exemple de code.  
  
 Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)



