---
title: "&lt;system_error&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 82f7876aca66524ba50b1e01b74437d8a2117976
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt;, opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&lt;](#operator_lt_)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Teste si l’objet situé à gauche de l’opérateur est égal à l’objet situé à droite.  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet dont l’égalité doit être vérifiée.|  
|`right`|Objet dont l’égalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets sont égaux ; **false** si les objets ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 Cette fonction retourne `left.category() == right.category() && left.value() == right.value()`.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Teste si l’objet situé à gauche de l’opérateur n’est pas égal à l’objet situé à droite.  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet dont l’inégalité doit être vérifiée.|  
|`right`|Objet dont l’inégalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet passé dans `left` n’est pas égal à l’objet passé dans `right` ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction retourne `!(left == right)`.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Vérifie si un objet est inférieur à l'objet passé en vue de leur comparaison.  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet à comparer.|  
|`right`|Objet à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet passé dans `left` est inférieur à l’objet passé dans `right` ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction permet de tester l'ordre des erreurs.  
  
## <a name="see-also"></a>Voir aussi  
 [<system_error>](../standard-library/system-error.md)



