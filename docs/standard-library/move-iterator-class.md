---
title: "move_iterator, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.move_iterator
- move_iterator
- iterator/std::move_iterator
- std::move_iterator
dev_langs:
- C++
helpviewer_keywords:
- move_iterator class
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
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
ms.openlocfilehash: b689b6363fbe7eff8d34d709f451e46bf9a92537
ms.lasthandoff: 02/24/2017

---
# <a name="moveiterator-class"></a>move_iterator, classe
Le modèle de classe `move_iterator` est un wrapper pour un itérateur. Le move_iterator fournit le même comportement que l'itérateur qu'il encapsule (ou stocke), à la différence près qu'il convertit l'opérateur de déréférence de l'itérateur stocké en une référence rvalue, convertissant ainsi une copie en déplacement. Pour plus d’informations sur les rvalues, consultez [Déclarateur de référence Rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="syntax"></a>Syntaxe  
```
class move_iterator;  
```
## <a name="remarks"></a>Remarques  
 La classe de modèle décrit un objet qui se comporte comme un itérateur, sauf lorsqu'il est déréférencé. Elle stocke un itérateur d’accès aléatoire de type `Iterator`, accessible par le biais de la fonction membre `base``()`. Toutes les opérations effectuées sur un `move_iterator` sont exécutées directement sur l'itérateur stocké, mais le résultat du `operator*` est implicitement converti en `value_type&&` pour créer une référence rvalue.  
  
 Un `move_iterator` peut être capable d'effectuer des opérations qui ne sont pas définies par l'itérateur encapsulé. Ces opérations ne doivent pas être utilisées.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[move_iterator](#move_iterator__move_iterator)|Constructeur des objets de type `move_iterator`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[move_iterator::iterator_type](#move_iterator__iterator_type)|Synonyme pour le paramètre du modèle `RandomIterator`.|  
|[move_iterator::iterator_category](#move_iterator__iterator_category)|Synonyme d'une expression `typename` plus longue du même nom, `iterator_category` représente les fonctionnalités générales de l'itérateur.|  
|[move_iterator::value_type](#move_iterator__value_type)|Synonyme d'une expression `typename` plus longue du même nom, `value_type` décrit le type des éléments de l'itérateur.|  
|[move_iterator::difference_type](#move_iterator__difference_type)|Synonyme d'une expression `typename` plus longue du même nom, `difference_type` décrit le type intégral requis pour exprimer des différences de valeur entre les éléments.|  
|[move_iterator::pointer](#move_iterator__pointer)|Synonyme du paramètre de modèle `RandomIterator`.|  
|[move_iterator::reference](#move_iterator__reference)|Synonyme de la référence `rvalue` `value_type&&`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[move_iterator::base](#move_iterator__base)|La fonction membre retourne l'itérateur stocké encapsulé par le `move_iterator`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[move_iterator::operator*](#move_iterator__operator_star)|Retourne `(reference)*``base``().`.|  
|[move_iterator::operator++](#move_iterator__operator_add_add)|Incrémente l'itérateur stocké. Le comportement exact varie selon qu'il s'agit d'une préincrémentation ou d'une postincrémentation.|  
|[move_iterator::operator--](#move_iterator__operator--)|Décrémente l'itérateur stocké. Le comportement exact varie selon qu'il s'agit d'une préincrémentation ou d'une postincrémentation.|  
|[move_iterator::operator-&gt;](#move_iterator__operator-_gt_)|Retourne `&**this`.|  
|[move_iterator::operator-](#move_iterator__operator-)|Retourne `move_iterator(*this) -=` en soustrayant d’abord la valeur située à droite de la position actuelle.|  
|[move_iterator::operator[]](#move_iterator__operator_at)|Retourne `(reference)*(*this + off)`. Permet de spécifier un décalage depuis la base actuelle pour obtenir la valeur de l'emplacement.|  
|[move_iterator::operator+](#move_iterator__operator_add)|Retourne la valeur `move_iterator(*this) +=`. Permet d'ajouter un décalage à la base pour obtenir la valeur de l'emplacement.|  
|[move_iterator::operator+=](#move_iterator__operator_add_eq)|Ajoute la valeur située à droite de l'itérateur stocké, et retourne `*this`.|  
|[move_iterator::operator-=](#move_iterator__operator-_eq)|Soustrait la valeur située à droite de l'itérateur stocké, et retourne `*this`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
##  <a name="a-namemoveiteratorbasea--moveiteratorbase"></a><a name="move_iterator__base"></a>  move_iterator::base  
 Retourne l'itérateur stocké pour ce `move_iterator`.  
  
```
RandomIterator base() const;
```  
  
### <a name="remarks"></a>Remarques  
 La fonction membre retourne l'itérateur stocké.  
  
##  <a name="a-namemoveiteratordifferencetypea--moveiteratordifferencetype"></a><a name="move_iterator__difference_type"></a>  move_iterator::difference_type  
 Le type `difference_type` est un `move_iterator``typedef` basé sur la caractéristique d’itérateur `difference_type`. Vous pouvez utiliser indifféremment l’un ou l’autre.  
  
```
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```    
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme de la caractéristique d'itérateur `typename iterator_traits<RandomIterator>::pointer`.  
  
##  <a name="a-namemoveiteratoriteratorcategorya--moveiteratoriteratorcategory"></a><a name="move_iterator__iterator_category"></a>  move_iterator::iterator_category  
 Le type `iterator_category` est un `move_iterator``typedef` basé sur la caractéristique d’itérateur `iterator_category`. Vous pouvez utiliser indifféremment l’un ou l’autre.  
  
```
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```    
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme de la caractéristique d'itérateur `typename iterator_traits<RandomIterator>::iterator_category`.  
  
##  <a name="a-namemoveiteratoriteratortypea--moveiteratoriteratortype"></a><a name="move_iterator__iterator_type"></a>  move_iterator::iterator_type  
 Le type `iterator_type` est basé sur le paramètre de modèle `RandomIterator` pour le modèle de classe `move_iterator`. Vous pouvez utiliser indifféremment l'un ou l'autre.  
  
```
typedef RandomIterator iterator_type;
```  
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme du paramètre de modèle `RandomIterator`.  
  
##  <a name="a-namemoveiteratormoveiteratora--moveiteratormoveiterator"></a><a name="move_iterator__move_iterator"></a>  move_iterator::move_iterator  
 Construit un itérateur de déplacement. Utilise le paramètre comme itérateur stocké.  
  
```
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Itérateur à utiliser comme itérateur stocké.  
  
### <a name="remarks"></a>Remarques  
 Le premier constructeur initialise l'itérateur stocké avec son constructeur par défaut. Les autres constructeurs initialisent l'itérateur stocké avec `base.base()`.  
  
##  <a name="a-namemoveiteratoroperatoraddeqa--moveiteratoroperator"></a><a name="move_iterator__operator_add_eq"></a>  move_iterator::operator+=  
 Ajoute un offset à l'itérateur stocké, pour que celui-ci pointe vers l'élément au nouvel emplacement actuel. L'opérateur déplace ensuite le nouvel élément actif.  
  
```
move_iterator& operator+=(difference_type _Off);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Offset à ajouter à la position actuelle pour déterminer la nouvelle position actuelle.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nouvel élément actif.  
  
### <a name="remarks"></a>Remarques  
 L'opérateur ajoute `_Off` à l'itérateur stocké. Il retourne ensuite `*this`.  
  
##  <a name="a-namemoveiteratoroperator-eqa--moveiteratoroperator-"></a><a name="move_iterator__operator-_eq"></a>  move_iterator::operator-=  
 Recule du nombre spécifié d'éléments. Cet opérateur soustrait un offset de l'itérateur stocké.  
  
```
move_iterator& operator-=(difference_type _Off);
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 L'opérateur évalue `*this += -_Off`. Il retourne ensuite `*this`.  
  
##  <a name="a-namemoveiteratoroperatoraddadda--moveiteratoroperator"></a><a name="move_iterator__operator_add_add"></a>  move_iterator::operator++  
 Incrémente l'itérateur stocké qui appartient à ce `move_iterator.`. L'élément actuel est accessible par l'opérateur d'incrémentation. L'élément suivant est accessible par l'opérateur de préincrémentation.  
  
```
move_iterator& operator++();
move_iterator operator++(int);
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 Le premier opérateur (préincrémentation) incrémente l'itérateur stocké. Il retourne ensuite `*this`.  
  
 Le deuxième opérateur (postincrémentation) effectue une copie de `*this` et évalue `++*this`. Ensuite, il retourne la copie.  
  
##  <a name="a-namemoveiteratoroperatoradda--moveiteratoroperator"></a><a name="move_iterator__operator_add"></a>  move_iterator::operator+  
 Retourne la position de l'itérateur avancée d'un nombre quelconque d'éléments.  
  
```
move_iterator operator+(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 L’opérateur retourne `move_iterator(*this) +=` `_Off`.  
  
##  <a name="a-namemoveiteratoroperatorata--moveiteratoroperator"></a><a name="move_iterator__operator_at"></a>  move_iterator::operator[]  
 Accorde l'accès à l'index de tableau aux éléments dans toute la plage du `move iterator`.  
  
```
reference operator[](difference_type _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 L'opérateur retourne `(reference)*(*this + _Off)`.  
  
##  <a name="a-namemoveiteratoroperator--a--moveiteratoroperator--"></a><a name="move_iterator__operator--"></a>  move_iterator::operator--  
 Les opérateurs membres de prédécrémentation et de postdécrémentation effectuent une décrémentation sur l'itérateur stocké.  
  
```
move_iterator& operator--();
move_iterator operator--();
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 Le premier opérateur membre (prédécrémentation) décrémente l'itérateur stocké. Il retourne ensuite `*this`.  
  
 Le deuxième opérateur (postdécrémentation) effectue une copie de `*this` et évalue `--*this`. Ensuite, il retourne la copie.  
  
##  <a name="a-namemoveiteratoroperator-a--moveiteratoroperator-"></a><a name="move_iterator__operator-"></a>  move_iterator::operator-  
 Décrémente l'itérateur stocké et retourne la valeur indiquée.  
  
```
move_iterator operator-(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
### <a name="remarks"></a>Remarques  
 L'opérateur retourne `move_iterator(*this) -= _Off`.  
  
##  <a name="a-namemoveiteratoroperatorstara--moveiteratoroperator"></a><a name="move_iterator__operator_star"></a>  move_iterator::operator*  
 Déréférence l'itérateur stocké et retourne la valeur. Se comporte comme une `rvalue reference` et exécute une assignation de déplacement. L'opérateur transfère l'élément actuel hors de l'itérateur de base. L'élément qui suit devient le nouvel élément actuel.  
  
```
reference operator*() const;
```  
  
### <a name="remarks"></a>Remarques  
 L'opérateur retourne `(reference)*``base``()`.  
  
##  <a name="a-namemoveiteratoroperator-gta--moveiteratoroperator-gt"></a><a name="move_iterator__operator-_gt_"></a>  move_iterator::operator-&gt;  
 Comme un `RandomIterator``operator->` normal, il fournit un accès aux champs qui appartiennent à l’élément actuel.  
  
```
pointer operator->() const;
```  
  
### <a name="remarks"></a>Remarques  
 L'opérateur retourne `&**this`.  
  
##  <a name="a-namemoveiteratorpointera--moveiteratorpointer"></a><a name="move_iterator__pointer"></a>  move_iterator::pointer  
 Le type `pointer` est un `typedef` basé sur l'itérateur aléatoire `RandomIterator` pour `move_iterator`. Vous pouvez utiliser indifféremment l'un ou l'autre.  
  
```
typedef RandomIterator  pointer;
```    
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme de `RandomIterator`.  
  
##  <a name="a-namemoveiteratorreferencea--moveiteratorreference"></a><a name="move_iterator__reference"></a>  move_iterator::reference  
 Le type `reference` est un `typedef` basé sur `value_type&&` pour `move_iterator`. Il peut être utilisé de manière interchangeable avec `value_type&&`.  
  
```
typedef value_type&& reference;
```    
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme de `value_type&&`, qui est une référence rvalue.  
  
##  <a name="a-namemoveiteratorvaluetypea--moveiteratorvaluetype"></a><a name="move_iterator__value_type"></a>  move_iterator::value_type  
 Le type `value_type` est un `move_iterator``typedef` basé sur la caractéristique d’itérateur `value_type`. Vous pouvez utiliser indifféremment l’un ou l’autre.  
  
```
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```    
  
### <a name="remarks"></a>Remarques  
 Le type est un synonyme de la caractéristique d'itérateur `typename iterator_traits<RandomIterator>::value_type`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<iterator>](../standard-library/iterator.md)   
 [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)   
 [Constructeurs de déplacement et opérateurs d’assignation de déplacement (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)   
 [Référence de bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




