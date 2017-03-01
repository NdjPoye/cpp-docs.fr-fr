---
title: initializer_list, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 2ac3e7fa456e5d3ff04bc5d974c87a9cbb055fea
ms.lasthandoff: 02/24/2017

---
# <a name="initializerlist-class"></a>initializer_list, classe
Fournit l'accès à un tableau d'éléments dans lequel chaque membre est du type spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Type>  
class initializer_list
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Type de données d'élément à stocker dans le `initializer_list`.|  

  
## <a name="remarks"></a>Notes  
 Un `initializer_list` peut être construit à l'aide d'une liste d'initialiseurs entre accolades :  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 Le compilateur transforme les listes d'initialiseurs entre accolades avec des éléments homogènes en un `initializer_list` chaque fois que la signature de fonction nécessite un `initializer_list`. Pour plus d’informations sur l’utilisation de `initializer_list`, consultez [Constructeurs d’initialisation uniforme et de délégation](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[initializer_list](../standard-library/forward-list-class.md#forward_list__forward_list)|Construit un objet de type `initializer_list`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|value_type|Type des éléments dans le `initializer_list`.|  
|reference|Type qui fournit une référence à un élément stocké dans le `initializer_list`.|  
|const_reference|Type qui fournit une référence constante à un élément dans le `initializer_list`.|  
|size_type|Type qui représente le nombre d'éléments dans le `initializer_list`.|  
|iterator|Type qui fournit un itérateur pour le `initializer_list`.|  
|const_iterator|Type qui fournit un itérateur constant pour le `initializer_list`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[begin](#initializer_list__begin)|Retourne un pointeur vers le premier élément d'une `initializer_list`.|  
|[end](#initializer_list__end)|Retourne un pointeur vers la position au-delà du dernier élément dans un `initializer_list`.|  
|[size](#initializer_list__size)|Retourne le nombre d'éléments d'un `initializer_list`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<initializer_list>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameinitializerlistbegina--initializerlistbegin"></a><a name="initializer_list__begin"></a>  initializer_list::begin  
 Retourne un pointeur vers le premier élément d'une `initializer_list`.  
  
```  
constexpr const InputIterator* begin() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le premier élément de la `initializer_list`. Si la liste est vide, le pointeur est le même pour le début et pour la fin de la liste.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameinitializerlistenda--initializerlistend"></a><a name="initializer_list__end"></a>  initializer_list::end  
 Retourne un pointeur vers la position au-delà du dernier élément dans un `initializer list`.  
  
```  
constexpr const InputIterator* end() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la position au-delà du dernier élément de la liste. Si la liste est vide, cela équivaut au pointeur vers le premier élément de la liste.  
  
##  <a name="a-nameinitializerlistinitializerlista--initializerlistinitializerlist"></a><a name="initializer_list__initializer_list"></a>  initializer_list::initializer_list  
 Construit un objet de type `initializer_list`.  
  
```  
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`First`|Position du premier élément de la plage d'éléments à copier.|  
|`Last`|Position du premier élément au-delà de la plage d'éléments à copier.|  
  
### <a name="remarks"></a>Notes  
 Une `initializer_list` est basée sur un tableau d'objets du type spécifié. La copie d'une `initializer_list` crée une deuxième instance d'une liste pointant vers les mêmes objets ; les objets sous-jacents ne sont pas copiés.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// initializer_list_class.cpp  
// compile with: /EHsc  
#include <initializer_list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    // Create an empty initializer_list c0  
    initializer_list <int> c0;  
  
    // Create an initializer_list c1 with 1 element  
    initializer_list <int> c1{ 3 };  
  
    // Create an initializer_list c2 with 5 elements   
    initializer_list <int> c2{ 5, 4, 3, 2, 1 };  
  
    // Create a copy, initializer_list c3, of initializer_list c2  
    initializer_list <int> c3(c2);  
  
    // Create a initializer_list c4 by copying the range c3[ first,  last)  
    const int* c3_ptr = c3.begin();  
    c3_ptr++;  
    c3_ptr++;  
    initializer_list <int> c4(c3.begin(), c3_ptr);  
  
    // Move initializer_list c4 to initializer_list c5  
    initializer_list <int> c5(move(c4));  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c2 =";  
    for (auto c : c2)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c3 =";  
    for (auto c : c3)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c5 =";  
    for (auto c : c5)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 3c2 = 5 4 3 2 1c3 = 5 4 3 2 1c4 = 5 4c5 = 5 4  
```  
  
##  <a name="a-nameinitializerlistsizea--initializerlistsize"></a><a name="initializer_list__size"></a>  initializer_list::size  
 Retourne le nombre d'éléments figurant dans la liste.  
  
```  
constexpr size_t size() const noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d'éléments dans la liste.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [<forward_list>](../standard-library/forward-list.md)


