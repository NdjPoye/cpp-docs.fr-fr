---
title: "&lt;thread&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7e849e8585b372b5b423a6c960aa926ac7d5cfec
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 Détermine si un objet `thread::id` est supérieur ou égal à un autre.  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `!(Left < Right)`  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 Détermine si un objet `thread::id` est supérieur à un autre.  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `Right < Left`  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 Détermine si un objet `thread::id` est inférieur ou égal à un autre.  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `!(Right < Left)`  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 Détermine si un objet `thread::id` est inférieur à un autre.  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si `Left` précède `Right` dans le classement total ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 L’opérateur définit un classement total sur tous les objets `thread::id`. Ces objets peuvent être utilisés comme clés dans les conteneurs associatifs.  
  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_neq"></a>  operator!=  
 Compare deux objets `thread::id` pour déterminer s'ils sont différents.  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `!(Left == Right)`  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_eq_eq"></a>  operator==  
 Compare deux objets `thread::id` pour déterminer s’ils sont égaux.  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread::id`.  
  
 `Right`  
 Objet droit `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les deux objets représentent le même thread d’exécution ou si aucun objet ne représente un thread d’exécution ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 Insère une représentation textuelle d’un objet `thread::id` dans un flux.  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>Paramètres  
 `Ostr`  
 Objet [basic_ostream](../standard-library/basic-ostream-class.md).  
  
 `Id`  
 Objet `thread::id`.  
  
### <a name="return-value"></a>Valeur de retour  
 `Ostr`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction insère `Id` dans `Ostr`.  
  
 Si deux objets `thread::id` sont considérés égaux, les représentations textuelles insérées de ces objets sont identiques.  
  
## <a name="see-also"></a>Voir aussi  
 [\<thread>](../standard-library/thread.md)




