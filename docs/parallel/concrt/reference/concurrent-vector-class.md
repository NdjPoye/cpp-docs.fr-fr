---
title: Classe concurrent_vector | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_vector/Concurrency::concurrent_vector
- concurrent_vector/concurrency::concurrent_vector
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: fdc84a03c562a4efa336f62c0cf0a7529c420f95
ms.lasthandoff: 02/24/2017

---
# <a name="concurrentvector-class"></a>Classe concurrent_vector
La classe `concurrent_vector` est une classe de conteneur de séquence qui autorise un accès aléatoire à tout élément. Elle permet les opérations d'ajout d'accès concurrentiel sécurisé, d'accès à un élément, d'accès à un itérateur et de traversée d'itérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
 private details::_Concurrent_vector_base_v4;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments à stocker dans le vecteur.  
  
 `_Ax`  
 Type qui représente l’objet allocateur stocké qui contient des informations sur l’allocation et la désallocation de mémoire pour le vecteur simultané. Cet argument est facultatif et sa valeur par défaut est `allocator<``T``>`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`allocator_type`|Type qui représente la classe d’allocateur pour le vecteur simultané.|  
|`const_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire un `const` élément dans un vecteur simultané.|  
|`const_pointer`|Type qui fournit un pointeur vers un `const` élément dans un vecteur simultané.|  
|`const_reference`|Type qui fournit une référence à un `const` élément stocké dans un vecteur simultané pour la lecture et l’exécution `const` operations.|  
|`const_reverse_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire un `const` élément dans le vecteur simultané.|  
|`difference_type`|Type qui fournit la distance signée entre deux éléments dans un vecteur simultané.|  
|`iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire n’importe quel élément dans un vecteur simultané. Modification d’un élément à l’aide de l’itérateur n’est pas concurrentiel.|  
|`pointer`|Type qui fournit un pointeur vers un élément dans un vecteur simultané.|  
|`reference`|Type qui fournit une référence à un élément stocké dans un vecteur simultané.|  
|`reverse_iterator`|Type qui fournit un itérateur à accès aléatoire capable de lire n’importe quel élément dans un vecteur simultané inversé. Modification d’un élément à l’aide de l’itérateur n’est pas concurrentiel.|  
|`size_type`|Type qui compte le nombre d’éléments dans un vecteur simultané.|  
|`value_type`|Type qui représente le type de données stocké dans un vecteur simultané.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[concurrent_vector, constructeur](#ctor)|Surchargé. Construit un vecteur simultané.|  
|[~ concurrent_vector, destructeur](#dtor)|Efface tous les éléments et détruit ce vecteur simultané.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Assign (méthode)](#assign)|Surchargé. Efface les éléments du vecteur simultané et lui attribue `_N` copie de `_Item`, ou les valeurs spécifiées par la plage d’itérateurs [ `_Begin`, `_End`). Cette méthode n’est pas concurrentiel.|  
|[AT (méthode)](#at)|Surchargé. Fournit l’accès à l’élément à l’index donné dans le vecteur simultané. Cette méthode est concurrentiel pour les opérations de lecture, ainsi que lors de l’augmentation du vecteur, tant que vous avez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.|  
|[Back (méthode)](#back)|Surchargé. Retourne une référence ou une `const` fait référence au dernier élément dans le vecteur simultané. Si le vecteur simultané est vide, la valeur de retour est non définie. Cette méthode est concurrentiel.|  
|[Begin (méthode)](#begin)|Surchargé. Retourne un itérateur de type `iterator` ou `const_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.|  
|[capacité (méthode)](#capacity)|Retourne la taille maximale que le vecteur simultané peut atteindre sans avoir à allouer plus de mémoire. Cette méthode est concurrentiel.|  
|[cbegin (méthode)](#cbegin)|Retourne un itérateur de type `const_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.|  
|[cend (méthode)](#cend)|Retourne un itérateur de type `const_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.|  
|[Clear (méthode)](#clear)|Efface tous les éléments dans le vecteur simultané. Cette méthode n’est pas concurrentiel.|  
|[crbegin (méthode)](#crbegin)|Retourne un itérateur de type `const_reverse_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.|  
|[crend (méthode)](#crend)|Retourne un itérateur de type `const_reverse_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.|  
|[Empty (méthode)](#empty)|Teste si le vecteur simultané est vide au moment où cette méthode est appelée. Cette méthode est concurrentiel.|  
|[End (méthode)](#end)|Surchargé. Retourne un itérateur de type `iterator` ou `const_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.|  
|[Front (méthode)](#front)|Surchargé. Retourne une référence ou une `const` référence au premier élément dans le vecteur simultané. Si le vecteur simultané est vide, la valeur de retour est non définie. Cette méthode est concurrentiel.|  
|[get_allocator (méthode)](#get_allocator)|Retourne une copie de l’allocateur utilisé pour construire le vecteur simultané. Cette méthode est concurrentiel.|  
|[grow_by (méthode)](#grow_by)|Surchargé. Augmente ce vecteur simultané par `_Delta` éléments. Cette méthode est concurrentiel.|  
|[grow_to_at_least (méthode)](#grow_to_at_least)|Augmente ce vecteur simultané jusqu'à ce qu’il ait au moins `_N` éléments. Cette méthode est concurrentiel.|  
|[max_size (méthode)](#max_size)|Retourne le nombre maximal d’éléments que du vecteur simultané peut contenir. Cette méthode est concurrentiel.|  
|[push_back (méthode)](#push_back)|Surchargé. Ajoute l’élément à la fin du vecteur simultané. Cette méthode est concurrentiel.|  
|[rbegin (méthode)](#rbegin)|Surchargé. Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.|  
|[rend (méthode)](#rend)|Surchargé. Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.|  
|[RESERVE (méthode)](#reserve)|Alloue suffisamment d’espace pour augmenter le vecteur simultané jusqu'à la taille `_N` sans avoir à allouer plus de mémoire ultérieurement. Cette méthode n’est pas concurrentiel.|  
|[Resize (méthode)](#resize)|Surchargé. Modifie la taille du vecteur simultané à la taille demandée, en supprimant ou en ajoutant des éléments si nécessaire. Cette méthode n’est pas concurrentiel.|  
|[shrink_to_fit (méthode)](#shrink_to_fit)|Compacte la représentation interne du vecteur simultané pour réduire la fragmentation et optimiser l’utilisation de la mémoire. Cette méthode n’est pas concurrentiel.|  
|[taille (méthode)](#size)|Retourne le nombre d’éléments dans le vecteur simultané. Cette méthode est concurrentiel.|  
|[swap (méthode)](#swap)|Échange le contenu de deux vecteurs simultanés. Cette méthode n’est pas concurrentiel.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator [] (opérateur)](#operator_at)|Surchargé. Fournit l’accès à l’élément à l’index donné dans le vecteur simultané. Cette méthode est concurrentiel pour les opérations de lecture, ainsi que lors de l’augmentation du vecteur, tant que vous avez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.|  
|[opérateur =, opérateur](#operator_eq)|Surchargé. Assigne le contenu d’un autre `concurrent_vector` objet à celui-ci. Cette méthode n’est pas concurrentiel.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur la `concurrent_vector` de classe, consultez la page [conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concurrent_vector.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameassigna-assign"></a><a name="assign"></a>attribuer 

 Efface les éléments du vecteur simultané et lui attribue `_N` copie de `_Item`, ou les valeurs spécifiées par la plage d’itérateurs [ `_Begin`, `_End`). Cette méthode n’est pas concurrentiel.  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Paramètres  
 `_InputIterator`  
 Le type de l’itérateur spécifié.  
  
 `_N`  
 Le nombre d’éléments à copier dans le vecteur simultané.  
  
 `_Item`  
 Référence à une valeur utilisée pour remplir le vecteur simultané.  
  
 `_Begin`  
 Un itérateur au premier élément de la plage source.  
  
 `_End`  
 Un itérateur vers l’élément suivant le dernier élément de la plage source.  
  
### <a name="remarks"></a>Remarques  
 `assign`n’est pas concurrentiel. Vous devez vous assurer qu’aucun autre thread n’appelez des méthodes sur le vecteur simultané lorsque vous appelez cette méthode.  
  
##  <a name="a-nameata-at"></a><a name="at"></a>à 

 Fournit l’accès à l’élément à l’index donné dans le vecteur simultané. Cette méthode est concurrentiel pour les opérations de lecture, ainsi que lors de l’augmentation du vecteur, tant que vous avez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’index de l’élément à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’élément à l’index donné.  
  
### <a name="remarks"></a>Remarques  
 La version de la fonction `at` qui retourne un non - `const` référence ne peut pas être utilisée pour écrire simultanément dans l’élément à partir de différents threads. Un objet de synchronisation différent doit être utilisé pour synchroniser la lecture simultanée et les opérations d’écriture dans le même élément de données.  
  
 La méthode lève `out_of_range` si `_Index` est supérieure ou égale à la taille du vecteur simultané, et `range_error` si l’index est pour une partie rompue du vecteur. Pour plus d’informations sur la façon dont un vecteur peut être endommagé, consultez [conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="a-namebacka-back"></a><a name="back"></a>Précédent 

 Retourne une référence ou une `const` fait référence au dernier élément dans le vecteur simultané. Si le vecteur simultané est vide, la valeur de retour est non définie. Cette méthode est concurrentiel.  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence ou une `const` fait référence au dernier élément dans le vecteur simultané.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>commencer 

 Retourne un itérateur de type `iterator` ou `const_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `iterator` ou `const_iterator` au début du vecteur simultané.  
  
##  <a name="a-namecapacitya-capacity"></a><a name="capacity"></a>capacité 

 Retourne la taille maximale que le vecteur simultané peut atteindre sans avoir à allouer plus de mémoire. Cette méthode est concurrentiel.  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille maximale que le vecteur simultané peut atteindre sans avoir à allouer plus de mémoire.  
  
### <a name="remarks"></a>Remarques  
 Contrairement à une bibliothèque C++ Standard `vector`, un `concurrent_vector` objet ne déplace pas les éléments existants s’il alloue plus de mémoire.  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 Retourne un itérateur de type `const_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `const_iterator` au début du vecteur simultané.  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 Retourne un itérateur de type `const_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `const_iterator` à la fin du vecteur simultané.  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Effacer 

 Efface tous les éléments dans le vecteur simultané. Cette méthode n’est pas concurrentiel.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Remarques  
 `clear`n’est pas concurrentiel. Vous devez vous assurer qu’aucun autre thread n’appelez des méthodes sur le vecteur simultané lorsque vous appelez cette méthode. `clear`ne libère pas de tableaux internes. Pour libérer des tableaux internes, appelez la fonction `shrink_to_fit` après `clear`.  
  
##  <a name="a-namectora-concurrentvector"></a><a name="ctor"></a>concurrent_vector 

 Construit un vecteur simultané.  
  
```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```  
  
### <a name="parameters"></a>Paramètres  
 `M`  
 Type d’allocateur du vecteur source.  
  
 `_InputIterator`  
 Type de l'itérateur d'entrée.  
  
 `_Al`  
 Classe allocator à utiliser avec cet objet.  
  
 `_Vector`  
 La source `concurrent_vector` objet à copier ou déplacer des éléments à partir de.  
  
 `_N`  
 La capacité initiale de la `concurrent_vector` objet.  
  
 `_Item`  
 La valeur des éléments dans l’objet construit.  
  
 `_Begin`  
 Position du premier élément dans la plage d'éléments à copier.  
  
 `_End`  
 Position du premier élément suivant la fin de la plage d'éléments à copier.  
  
### <a name="remarks"></a>Notes  
 Tous les constructeurs stockent un objet allocateur `_Al` et initialisent le vecteur.  
  
 Le premier constructeur spécifient un vecteur initial vide et spécifie explicitement le type d’allocateur. à utiliser.  
  
 Les deuxième et troisièmes constructeurs spécifient une copie du vecteur simultané `_Vector`.  
  
 Le quatrième constructeur spécifie une opération de déplacement du vecteur simultané `_Vector`.  
  
 Le cinquième constructeur spécifie une répétition d’un nombre spécifié ( `_N`) des éléments de la valeur par défaut pour la classe `T`.  
  
 Le sixième constructeur spécifie une répétition de ( `_N`) éléments ayant la valeur `_Item`.  
  
 Le dernier constructeur spécifie les valeurs fournies par la plage d’itérateurs [ `_Begin`, `_End`).  
  
##  <a name="a-namedtora-concurrentvector"></a><a name="dtor"></a>~ concurrent_vector 

 Efface tous les éléments et détruit ce vecteur simultané.  
  
```
~concurrent_vector();
```  
  
##  <a name="a-namecrbegina-crbegin"></a><a name="crbegin"></a>crbegin 

 Retourne un itérateur de type `const_reverse_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `const_reverse_iterator` au début du vecteur simultané.  
  
##  <a name="a-namecrenda-crend"></a><a name="crend"></a>crend 

 Retourne un itérateur de type `const_reverse_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `const_reverse_iterator` à la fin du vecteur simultané.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>vide 

 Teste si le vecteur simultané est vide au moment où cette méthode est appelée. Cette méthode est concurrentiel.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur était vide au moment où la fonction a été appelée, `false` dans le cas contraire.  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>fin 

 Retourne un itérateur de type `iterator` ou `const_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `iterator` ou `const_iterator` à la fin du vecteur simultané.  
  
##  <a name="a-namefronta-front"></a><a name="front"></a>premier plan 

 Retourne une référence ou une `const` référence au premier élément dans le vecteur simultané. Si le vecteur simultané est vide, la valeur de retour est non définie. Cette méthode est concurrentiel.  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence ou une `const` référence au premier élément dans le vecteur simultané.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Retourne une copie de l’allocateur utilisé pour construire le vecteur simultané. Cette méthode est concurrentiel.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une copie de l’allocateur utilisé pour construire le `concurrent_vector` objet.  
  
##  <a name="a-namegrowbya-growby"></a><a name="grow_by"></a>grow_by 

 Augmente ce vecteur simultané par `_Delta` éléments. Cette méthode est concurrentiel.  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Delta`  
 Le nombre d’éléments à ajouter à l’objet.  
  
 `_Item`  
 La valeur pour initialiser les nouveaux éléments avec.  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur au premier élément ajouté.  
  
### <a name="remarks"></a>Remarques  
 Si `_Item` n’est pas spécifié, les nouveaux éléments sont construits par défaut.  
  
##  <a name="a-namegrowtoatleasta-growtoatleast"></a><a name="grow_to_at_least"></a>grow_to_at_least 

 Augmente ce vecteur simultané jusqu'à ce qu’il ait au moins `_N` éléments. Cette méthode est concurrentiel.  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>Paramètres  
 `_N`  
 La nouvelle taille minimale pour le `concurrent_vector` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le début de la séquence ajoutée, ou à l’élément à l’index `_N` si aucun élément ont été ajoutés.  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 Retourne le nombre maximal d’éléments que du vecteur simultané peut contenir. Cette méthode est concurrentiel.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal d’éléments de la `concurrent_vector` objet peut contenir.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Assigne le contenu d’un autre `concurrent_vector` objet à celui-ci. Cette méthode n’est pas concurrentiel.  
  
```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```  
  
### <a name="parameters"></a>Paramètres  
 `M`  
 Type d’allocateur du vecteur source.  
  
 `_Vector`  
 Objet `concurrent_vector` source.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `concurrent_vector` objet.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>operator] 

 Fournit l’accès à l’élément à l’index donné dans le vecteur simultané. Cette méthode est concurrentiel pour les opérations de lecture, ainsi que lors de l’augmentation du vecteur, tant que vous avez vérifié que la valeur `_Index` est inférieure à la taille du vecteur simultané.  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’index de l’élément à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’élément à l’index donné.  
  
### <a name="remarks"></a>Remarques  
 La version de `operator []` qui retourne un non - `const` référence ne peut pas être utilisée pour écrire simultanément dans l’élément à partir de différents threads. Un objet de synchronisation différent doit être utilisé pour synchroniser la lecture simultanée et les opérations d’écriture dans le même élément de données.  
  
 Aucune vérification est effectuée pour vous assurer que des limites `_Index` est un index valide dans le vecteur simultané.  
  
##  <a name="a-namepushbacka-pushback"></a><a name="push_back"></a>push_back 

 Ajoute l’élément à la fin du vecteur simultané. Cette méthode est concurrentiel.  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Item`  
 La valeur à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de l’élément ajouté.  
  
##  <a name="a-namerbegina-rbegin"></a><a name="rbegin"></a>rbegin 

 Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` au début du vecteur simultané. Cette méthode est concurrentiel.  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `reverse_iterator` ou `const_reverse_iterator` au début du vecteur simultané.  
  
##  <a name="a-namerenda-rend"></a><a name="rend"></a>rend) 

 Retourne un itérateur de type `reverse_iterator` ou `const_reverse_iterator` à la fin du vecteur simultané. Cette méthode est concurrentiel.  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de type `reverse_iterator` ou `const_reverse_iterator` à la fin du vecteur simultané.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>réserve 

 Alloue suffisamment d’espace pour augmenter le vecteur simultané jusqu'à la taille `_N` sans avoir à allouer plus de mémoire ultérieurement. Cette méthode n’est pas concurrentiel.  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>Paramètres  
 `_N`  
 Le nombre d’éléments à réserver pour un espace.  
  
### <a name="remarks"></a>Remarques  
 `reserve`n’est pas concurrentiel. Vous devez vous assurer qu’aucun autre thread n’appelez des méthodes sur le vecteur simultané lorsque vous appelez cette méthode. La capacité du vecteur simultané après que la méthode peut être plus grande que la réservation demandée.  
  
##  <a name="a-nameresizea-resize"></a><a name="resize"></a>redimensionner 

 Modifie la taille du vecteur simultané à la taille demandée, en supprimant ou en ajoutant des éléments si nécessaire. Cette méthode n’est pas concurrentiel.  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `_N`  
 La nouvelle taille de la concurrent_vector.  
  
 `val`  
 La valeur des nouveaux éléments ajoutés au vecteur si la nouvelle taille est supérieure à la taille d’origine. Si la valeur est omise, les nouveaux objets sont attribués à la valeur par défaut de leur type.  
  
### <a name="remarks"></a>Remarques  
 Si la taille du conteneur est inférieure à la taille demandée, les éléments sont ajoutés au vecteur jusqu'à ce qu’il atteigne la taille demandée. Si la taille du conteneur est supérieure à la taille demandée, les éléments le plus proche de la fin du conteneur sont supprimés jusqu'à ce que le conteneur atteigne la taille `_N`. Si la taille actuelle du conteneur est égale à la taille demandée, aucune action n'est effectuée.  
  
 `resize`n’est pas l’accès concurrentiel sécurisé. Vous devez vous assurer qu’aucun autre thread n’appelez des méthodes sur le vecteur simultané lorsque vous appelez cette méthode.  
  
##  <a name="a-nameshrinktofita-shrinktofit"></a><a name="shrink_to_fit"></a>shrink_to_fit 

 Compacte la représentation interne du vecteur simultané pour réduire la fragmentation et optimiser l’utilisation de la mémoire. Cette méthode n’est pas concurrentiel.  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode sera en interne réaffecter les éléments du déplacement de mémoire, invalidant tous les itérateurs. `shrink_to_fit`n’est pas concurrentiel. Vous devez vous assurer qu’aucun autre thread n’appelez des méthodes sur le vecteur simultané lorsque vous appelez cette fonction.  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>taille 

 Retourne le nombre d’éléments dans le vecteur simultané. Cette méthode est concurrentiel.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans ce `concurrent_vector` objet.  
  
### <a name="remarks"></a>Notes  
 La taille retournée est garantie pour inclure tous les éléments ajoutés par les appels à la fonction `push_back`, ou les opérations terminées avant d’appeler cette méthode de développement. Toutefois, il peut également inclure des éléments alloués mais encore en cours d’élaboration par les appels simultanés aux méthodes de croissance.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>échange 

 Échange le contenu de deux vecteurs simultanés. Cette méthode n’est pas concurrentiel.  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Vector`  
 Le `concurrent_vector` objet échanger le contenu avec.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md)




