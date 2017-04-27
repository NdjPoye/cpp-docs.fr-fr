---
title: "&lt;forward_list&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a560de0a7587b5552fc663bdd2b44734a66b5f73
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  operator==  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur est égal à l’objet de liste forward_list situé à droite.  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="remarks"></a>Notes  
 Cette fonction de modèle surcharge `operator==` pour comparer deux objets de la classe de modèle `forward_list`. La fonction retourne `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.  
  
##  <a name="operator_neq"></a>  operator!=  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur n’est pas égal à l’objet de liste forward_list situé à droite.  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les listes ne sont pas égales ; **false** si les listes sont égales.  
  
### <a name="remarks"></a>Notes  
 Cette fonction de modèle retourne `!(left == right)`.  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur est inférieur à l’objet de liste forward_list situé à droite.  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la liste à gauche de l’opérateur est inférieure et non égale à la liste à droite de l’opérateur ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction de modèle surcharge `operator<` pour comparer deux objets de la classe de modèle `forward_list`. La fonction retourne `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur est inférieur ou égal à l’objet de liste forward_list situé à droite.  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la liste à gauche de l’opérateur est inférieure ou égale à la liste à droite de l’opérateur ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction de modèle retourne `!(right < left)`.  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur est supérieur à l’objet de liste forward_list situé à droite.  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la liste à gauche de l’opérateur est supérieure à la liste à droite de l’opérateur ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction de modèle retourne `right < left`.  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 Vérifie si l’objet de liste forward_list à gauche de l’opérateur est supérieur ou égal à l’objet de liste forward_list situé à droite.  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la liste forward_list à gauche de l’opérateur est supérieure ou égale à la liste forward_list à droite de l’opérateur ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle retourne `!(left < right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [<forward_list>](../standard-library/forward-list.md)




