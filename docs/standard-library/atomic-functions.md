---
title: '&lt;atomic&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3b10205d490f9ac7a4f69ef01fc0da30fe7012ed
ms.lasthandoff: 02/24/2017

---
# <a name="ltatomicgt-functions"></a>&lt;atomic&gt;, fonctions
||||  
|-|-|-|  
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong_function)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit_function)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak_function)|  
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit_function)|[atomic_exchange](#atomic_exchange_function)|[atomic_exchange_explicit](#atomic_exchange_explicit_function)|  
|[atomic_fetch_add](#atomic_fetch_add_function)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit_function)|[atomic_fetch_and](#atomic_fetch_and_function)|  
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit_function)|[atomic_fetch_or](#atomic_fetch_or_function)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit_function)|  
|[atomic_fetch_sub](#atomic_fetch_sub_function)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit_function)|[atomic_fetch_xor](#atomic_fetch_xor_function)|  
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit_function)|[atomic_flag_clear](#atomic_flag_clear_function)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit_function)|  
|[atomic_flag_test_and_set](#atomic_flag_test_and_set_function)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit_function)|[atomic_init](#atomic_init_function)|  
|[atomic_is_lock_free](#atomic_is_lock_free_function)|[atomic_load](#atomic_load_function)|[atomic_load_explicit](#atomic_load_explicit_function)|  
|[atomic_signal_fence](#atomic_signal_fence_function)|[atomic_store](#atomic_store_function)|[atomic_store_explicit](#atomic_store_explicit_function)|  
|[atomic_thread_fence](#atomic_thread_fence_function)|[kill_dependency](#kill_dependency_function)|  
  
##  <a name="a-nameatomiccompareexchangestrongfunctiona--atomiccompareexchangestrong"></a><a name="atomic_compare_exchange_strong_function"></a>  atomic_compare_exchange_strong  
 Effectue une opération atomique de comparaison et d’échange.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Exp`  
 Pointeur vers une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
### <a name="return-value"></a>Valeur de retour  
 `bool` qui indique le résultat de la comparaison de valeurs.  
  
### <a name="remarks"></a>Notes  
 Cette méthode effectue une opération atomique de comparaison et d’échange à l’aide d’arguments implicites `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Pour plus d’informations, consultez [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit_function).  
  
##  <a name="a-nameatomiccompareexchangestrongexplicitfunctiona--atomiccompareexchangestrongexplicit"></a><a name="atomic_compare_exchange_strong_explicit_function"></a>  atomic_compare_exchange_strong_explicit  
 Effectue une opération *atomique de comparaison et d’échange*.  
  
```
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Exp`  
 Pointeur vers une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
 `Order1`  
 Premier argument [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 `Order2`  
 Deuxième argument `memory_order`. La valeur de `Order2` ne peut pas être `memory_order_release` ou `memory_order_acq_rel`, elle ne peut pas être supérieure à la valeur de `Order1`.  
  
### <a name="return-value"></a>Valeur de retour  
 `bool` qui indique le résultat de la comparaison de valeurs.  
  
### <a name="remarks"></a>Notes  
 Une *opération atomique de comparaison et d’échange* compare la valeur stockée dans l’objet désignée par `Atom` à la valeur désignée par `Exp`. Si les valeurs sont égales, la valeur stockée dans l’objet désignée par `atom` est remplacée par `Val` à l’aide d’une opération `read-modify-write` et en appliquant les contraintes d’ordre de mémoire spécifiées par `Order1`. Si les valeurs ne sont pas égales, l’opération remplace la valeur désignée par `Exp` par la valeur stockée dans l’objet désignée par `Atom` et applique les contraintes d’ordre de mémoire spécifiées par `Order2`.  
  
##  <a name="a-nameatomiccompareexchangeweakfunctiona--atomiccompareexchangeweak"></a><a name="atomic_compare_exchange_weak_function"></a>  atomic_compare_exchange_weak  
 Effectue une opération *atomique faible de comparaison et d’échange*.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Exp`  
 Pointeur vers une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
### <a name="return-value"></a>Valeur de retour  
 `bool` qui indique le résultat de la comparaison de valeurs.  
  
### <a name="remarks"></a>Notes  
 Cette méthode effectue une *opération atomique faible de comparaison et d’échange* qui a des arguments implicites `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Pour plus d’informations, consultez [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit_function).  
  
##  <a name="a-nameatomiccompareexchangeweakexplicitfunctiona--atomiccompareexchangeweakexplicit"></a><a name="atomic_compare_exchange_weak_explicit_function"></a>  atomic_compare_exchange_weak_explicit  
 Effectue une opération *atomique faible de comparaison et d’échange*.  
  
```
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp, 
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Exp`  
 Pointeur vers une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
 `Order1`  
 Premier argument [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 `Order2`  
 Deuxième argument `memory_order`. La valeur de `Order2` ne peut pas être `memory_order_release` ou `memory_order_acq_rel`, elle ne peut pas être non plus supérieure à la valeur de `Order1`.  
  
### <a name="return-value"></a>Valeur de retour  
 `bool` qui indique le résultat de la comparaison de valeurs.  
  
### <a name="remarks"></a>Notes  
 Une *opération atomique de comparaison et d’échange* compare la valeur stockée dans l’objet désignée par `Atom` à la valeur désignée par `Exp`. Si les valeurs sont égales, l’opération remplace la valeur stockée dans l’objet désignée par `Atom` par `Val` à l’aide d’une opération `read-modify-write` et en appliquant les contraintes d’ordre de mémoire spécifiées par `Order1`. Si les valeurs ne sont pas égales, l’opération remplace la valeur désignée par `Exp` par la valeur stockée dans l’objet désignée par `Atom` et applique les contraintes d’ordre de mémoire spécifiées par `Order2`.  
  
 Une opération atomique *faible* de comparaison et d’échange effectue un échange si les valeurs comparées sont égales. Toutefois, si les valeurs ne sont pas égales, l’opération d’échange n’est pas garantie.  
  
##  <a name="a-nameatomicexchangefunctiona--atomicexchange"></a><a name="atomic_exchange_function"></a>  atomic_exchange  
 Utilise `Value` pour remplacer la valeur stockée de `Atom`.  
  
```
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur stockée de `Atom` avant l’échange.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_exchange` effectue une opération `read-modify-write` pour échanger la valeur stockée dans `Atom` avec `Value`, à l’aide de `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicexchangeexplicitfunctiona--atomicexchangeexplicit"></a><a name="atomic_exchange_explicit_function"></a>  atomic_exchange_explicit  
 Remplace la valeur stockée de `Atom` par `Value`.  
  
```
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur stockée de `Atom` avant l’échange.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_exchange_explicit` effectue une opération `read-modify-write` pour échanger la valeur stockée dans `Atom` avec `Value`, en respectant les contraintes d’ordre de mémoire spécifiées par `Order`.  
  
##  <a name="a-nameatomicfetchaddfunctiona--atomicfetchadd"></a><a name="atomic_fetch_add_function"></a>  atomic_fetch_add  
 Ajoute une valeur à une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>  
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>  
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke un pointeur de type `T`.  
  
 `Value`  
 Valeur de type `ptrdiff_t`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur du pointeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_add` effectue une opération `read-modify-write` pour ajouter de manière atomique `Value` à la valeur stockée dans `Atom`, à l’aide de la contrainte `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 Quand le type atomique est `atomic_address`, `Value` a le type `ptrdiff_t` et l’opération traite le pointeur stocké comme un `char *`.  
  
 Cette opération est également surchargée pour les types intégraux :  
  
```
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="a-nameatomicfetchaddexplicitfunctiona--atomicfetchaddexplicit"></a><a name="atomic_fetch_add_explicit_function"></a>  atomic_fetch_add_explicit  
 Ajoute une valeur à une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>  
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom, 
    ptrdiff_t Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke un pointeur de type `T`.  
  
 `Value`  
 Valeur de type `ptrdiff_t`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur du pointeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_add_explicit` effectue une opération `read-modify-write` pour ajouter de manière atomique `Value` à la valeur stockée dans `Atom`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées par `Order`.  
  
 Quand le type atomique est `atomic_address`, `Value` a le type `ptrdiff_t` et l’opération traite le pointeur stocké comme un `char *`.  
  
 Cette opération est également surchargée pour les types intégraux :  
  
```cpp  
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="a-nameatomicfetchandfunctiona--atomicfetchand"></a><a name="atomic_fetch_and_function"></a>  atomic_fetch_and  
 Effectue une opération `and` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_and` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `and` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, à l’aide de la contrainte `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchandexplicitfunctiona--atomicfetchandexplicit"></a><a name="atomic_fetch_and_explicit_function"></a>  atomic_fetch_and_explicit  
 Effectue une opération `and` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
    
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_and_explicit` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `and` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, en respectant les contraintes de mémoire spécifiées par `Order`.  
  
##  <a name="a-nameatomicfetchorfunctiona--atomicfetchor"></a><a name="atomic_fetch_or_function"></a>  atomic_fetch_or  
 Effectue une opération `or` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_or` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `or` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, à l’aide de `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchorexplicitfunctiona--atomicfetchorexplicit"></a><a name="atomic_fetch_or_explicit_function"></a>  atomic_fetch_or_explicit  
 Effectue une opération `or` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_or_explicit` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `or` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées par `Order`.  
  
##  <a name="a-nameatomicfetchsubfunctiona--atomicfetchsub"></a><a name="atomic_fetch_sub_function"></a>  atomic_fetch_sub  
 Soustrait une valeur d’une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>  
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>  
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke un pointeur de type `T`.  
  
 `Value`  
 Valeur de type `ptrdiff_t`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur du pointeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_sub` effectue une opération `read-modify-write` pour soustraire de manière atomique `Value` de la valeur stockée dans `Atom`, à l’aide de la contrainte `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
 Quand le type atomique est `atomic_address`, `Value` a le type `ptrdiff_t` et l’opération traite le pointeur stocké comme un `char *`.  
  
 Cette opération est également surchargée pour les types intégraux :  
  
```
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="a-nameatomicfetchsubexplicitfunctiona--atomicfetchsubexplicit"></a><a name="atomic_fetch_sub_explicit_function"></a>  atomic_fetch_sub_explicit  
 Soustrait une valeur d’une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>  
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>  
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke un pointeur de type `T`.  
  
 `Value`  
 Valeur de type `ptrdiff_t`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur du pointeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_sub_explicit` effectue une opération `read-modify-write` pour soustraire de manière atomique `Value` de la valeur stockée dans `Atom`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées par `Order`.  
  
 Quand le type atomique est `atomic_address`, `Value` a le type `ptrdiff_t` et l’opération traite le pointeur stocké comme un `char *`.  
  
 Cette opération est également surchargée pour les types intégraux :  
  
```cpp  
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```  
  
##  <a name="a-nameatomicfetchxorfunctiona--atomicfetchxor"></a><a name="atomic_fetch_xor_function"></a>  atomic_fetch_xor  
 Effectue une opération `exclusive or` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept; 

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_xor` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `exclusive or` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, à l’aide de `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicfetchxorexplicitfunctiona--atomicfetchxorexplicit"></a><a name="atomic_fetch_xor_explicit_function"></a>  atomic_fetch_xor_explicit  
 Effectue une opération `exclusive or` au niveau du bit sur une valeur et une valeur existante stockée dans un objet `atomic`.  
  
```
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
    
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom, 
    T Value,
    memory_order Order) noexcept; 
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
 `Value`  
 Valeur de type `T`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur contenue dans l’objet atomique immédiatement avant l’opération.  
  
### <a name="remarks"></a>Notes  
 La fonction `atomic_fetch_xor_explicit` effectue une opération `read-modify-write` pour remplacer la valeur stockée de `Atom` par une opération `exclusive or` au niveau du bit de `Value` et la valeur actuelle stockée dans `Atom`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées par `Order`.  
  
##  <a name="a-nameatomicflagclearfunctiona--atomicflagclear"></a><a name="atomic_flag_clear_function"></a>  atomic_flag_clear  
 Définit l’indicateur `bool` dans un objet [atomic_flag](../standard-library/atomic-flag-structure.md) avec la valeur `false`, en respectant `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Flag`  
 Pointeur vers un objet `atomic_flag`.  
  
##  <a name="a-nameatomicflagclearexplicitfunctiona--atomicflagclearexplicit"></a><a name="atomic_flag_clear_explicit_function"></a>  atomic_flag_clear_explicit  
 Définit l’indicateur `bool` dans un objet [atomic_flag](../standard-library/atomic-flag-structure.md) avec la valeur `false`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées.  
  
```
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Flag`  
 Pointeur vers un objet `atomic_flag`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicflagtestandsetfunctiona--atomicflagtestandset"></a><a name="atomic_flag_test_and_set_function"></a>  atomic_flag_test_and_set  
 Définit l’indicateur `bool` dans un objet [atomic_flag](../standard-library/atomic-flag-structure.md) avec la valeur `true`, en respectant les contraintes de `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Flag`  
 Pointeur vers un objet `atomic_flag`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur initiale de `Flag`.  
  
##  <a name="a-nameatomicflagtestandsetexplicitfunctiona--atomicflagtestandsetexplicit"></a><a name="atomic_flag_test_and_set_explicit_function"></a>  atomic_flag_test_and_set_explicit  
 Définit l’indicateur `bool` dans un objet [atomic_flag](../standard-library/atomic-flag-structure.md) avec la valeur `true`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées.  
  
```
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Flag`  
 Pointeur vers un objet `atomic_flag`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur initiale de `Flag`.  
  
##  <a name="a-nameatomicinitfunctiona--atomicinit"></a><a name="atomic_init_function"></a>  atomic_init  
 Définit la valeur stockée dans un objet `atomic`.  
  
```
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
### <a name="remarks"></a>Notes  
 `atomic_init` n’est pas une opération atomique. Elle n’est pas thread‑safe.  
  
##  <a name="a-nameatomicislockfreefunctiona--atomicislockfree"></a><a name="atomic_is_lock_free_function"></a>  atomic_is_lock_free  
 Spécifie si les opérations atomiques sur un objet `atomic` sont *sans verrou*.  
  
```
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui stocke une valeur de type `T`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si des opérations atomiques sur `Atom` sont sans verrou ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Un type atomique est sans verrou si aucune opération atomique sur ce type utilise un verrou. Si cette fonction retourne la valeur true, le type peut être utilisé dans les gestionnaires de signal.  
  
##  <a name="a-nameatomicloadfunctiona--atomicload"></a><a name="atomic_load_function"></a>  atomic_load  
 Récupère la valeur stockée dans un objet `atomic`.  
  
```
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui contient une valeur de type `Ty`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur récupérée stockée dans `Atom`.  
  
### <a name="remarks"></a>Notes  
 `atomic_load` utilise implicitement `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicloadexplicitfunctiona--atomicloadexplicit"></a><a name="atomic_load_explicit_function"></a>  atomic_load_explicit  
 Récupère la valeur stockée dans un objet `atomic`, en respectant un [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifié.  
  
```
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui contient une valeur de type `Ty`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum). N’utilisez pas `memory_order_release` ou `memory_order_acq_rel`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur récupérée stockée dans `Atom`.  
  
##  <a name="a-nameatomicsignalfencefunctiona--atomicsignalfence"></a><a name="atomic_signal_fence_function"></a>  atomic_signal_fence  
 Agit comme une *délimitation* (c’est-à-dire une primitive de synchronisation de mémoire qui applique un ordre entre les opérations de chargement/stockage) entre d’autres délimitations d’un thread d’appel qui ont des gestionnaires de signal exécutés dans le même thread.  
  
```
inline void atomic_signal_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Order`  
 Contrainte d’ordre de mémoire qui détermine le type de délimitation.  
  
### <a name="remarks"></a>Notes  
 L’argument `Order` détermine le type de délimitation.  
  
|||  
|-|-|  
|`memory_order_relaxed`|La délimitation est sans effet.|  
|`memory_order_consume`|La délimitation est une délimitation d’acquisition.|  
|`memory_order_acquire`|La délimitation est une délimitation d’acquisition.|  
|`memory_order_release`|La délimitation est une délimitation de libération.|  
|`memory_order_acq_rel`|La délimitation est une délimitation d’acquisition et de libération.|  
|`memory_order_seq_cst`|La délimitation est une délimitation d’acquisition et de libération, et est cohérente de manière séquentielle.|  
  
##  <a name="a-nameatomicstorefunctiona--atomicstore"></a><a name="atomic_store_function"></a>  atomic_store  
 Stocke de manière atomique une valeur dans un objet atomique.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet atomique qui contient une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
### <a name="remarks"></a>Notes  
 `atomic_store` stocke `Value` dans l’objet désigné par `Atom`, en respectant la contrainte `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicstoreexplicitfunctiona--atomicstoreexplicit"></a><a name="atomic_store_explicit_function"></a>  atomic_store_explicit  
 Stocke de manière atomique une valeur dans un objet atomique.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom, 
    Ty Value, 
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom, 
    T Value, 
    memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Atom`  
 Pointeur vers un objet `atomic` qui contient une valeur de type `Ty`.  
  
 `Value`  
 Valeur de type `Ty`.  
  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum). N’utilisez pas `memory_order_consume`, `memory_order_acquire` ou `memory_order_acq_rel`.  
  
### <a name="remarks"></a>Notes  
 `atomic_store` stocke `Value` dans l’objet désigné par `Atom`, en respectant le `memory_order` spécifié par `Order`.  
  
##  <a name="a-nameatomicthreadfencefunctiona--atomicthreadfence"></a><a name="atomic_thread_fence_function"></a>  atomic_thread_fence  
 Agit comme une *délimitation* (c’est-à-dire, une primitive de synchronisation de mémoire qui applique un ordre entre les opérations de chargement/stockage) sans opération atomique associée.  
  
```
inline void atomic_thread_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Order`  
 Contrainte d’ordre de mémoire qui détermine le type de délimitation.  
  
### <a name="remarks"></a>Notes  
 L’argument `Order` détermine le type de délimitation.  
  
|||  
|-|-|  
|`memory_order_relaxed`|La délimitation est sans effet.|  
|`memory_order_consume`|La délimitation est une délimitation d’acquisition.|  
|`memory_order_acquire`|La délimitation est une délimitation d’acquisition.|  
|`memory_order_release`|La délimitation est une délimitation de libération.|  
|`memory_order_acq_rel`|La délimitation est une délimitation d’acquisition et de libération.|  
|`memory_order_seq_cst`|La délimitation est une délimitation d’acquisition et de libération, et est cohérente de manière séquentielle.|  
  
##  <a name="a-namekilldependencyfunctiona--killdependency"></a><a name="kill_dependency_function"></a>  kill_dependency  
 Supprime une dépendance.  
  
```
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Arg`  
 Valeur de type `Ty`.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour est `Arg`. L’évaluation de `Arg` ne comprend pas de dépendance à l’appel de fonction. En arrêtant une chaîne de dépendance possible, la fonction peut permettre au compilateur de générer du code plus efficace.  
  
## <a name="see-also"></a>Voir aussi  
 [\<atomic>](../standard-library/atomic.md)




