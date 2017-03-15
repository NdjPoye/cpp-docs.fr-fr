---
title: error_category, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::error_category
- system_error/std::error_category
- error_category
- std.error_category
dev_langs:
- C++
helpviewer_keywords:
- error_category class
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 7700ffce8b04f9caad33c08f03f0585c29a43efd
ms.lasthandoff: 02/24/2017

---
# <a name="errorcategory-class"></a>error_category, classe
Représente la base abstraite et commune d’objets qui décrit une catégorie de codes d’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class error_category;
```  
  
## <a name="remarks"></a>Notes  
 Deux objets prédéfinis implémentent `error_category` : [generic_category](../standard-library/system-error-functions.md#generic_category) et [system_category](../standard-library/system-error-functions.md#system_category).  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[value_type](#error_category__value_type)|Type qui représente la valeur de code d’erreur stockée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[default_error_condition](#error_category__default_error_condition)|Stocke la valeur de code d’erreur d’un objet de condition d’erreur.|  
|[equivalent](#error_category__equivalent)|Retourne une valeur qui spécifie si les objets d’erreur sont équivalents.|  
|[message](#error_category__message)|Retourne le nom du code d’erreur spécifié.|  
|[name](#error_category__name)|Retourne le nom de la catégorie.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](#error_category__operator_eq_eq)|Vérifie l’égalité d’objets `error_category`.|  
|[operator!=](#error_category__operator_neq)|Vérifie l’inégalité d’objets `error_category`.|  
|[operator<](#error_category__operator_lt_)|Vérifie si l’objet [error_category](../standard-library/error-category-class.md) est inférieur à l’objet `error_category` transmis pour la comparaison.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameerrorcategorydefaulterrorconditiona--errorcategorydefaulterrorcondition"></a><a name="error_category__default_error_condition"></a>  error_category::default_error_condition  
 Stocke la valeur de code d’erreur d’un objet de condition d’erreur.  
  
```
virtual error_condition default_error_condition(int _Errval) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errval`|Valeur de code d’erreur à stocker dans [error_condition](../standard-library/error-condition-class.md).|  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `error_condition(_Errval, *this)`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorcategoryequivalenta--errorcategoryequivalent"></a><a name="error_category__equivalent"></a>  error_category::equivalent  
 Retourne une valeur qui spécifie si les objets d’erreur sont équivalents.  
  
```
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errval`|Valeur de code d’erreur à comparer.|  
|`_Cond`|Objet [error_condition](../standard-library/error-condition-class.md) à comparer.|  
|`_Code`|Objet [error_code](../standard-library/error-code-class.md) à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la catégorie et la valeur sont égales ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre retourne `*this == _Cond.category() && _Cond.value() == _Errval`.  
  
 La deuxième fonction membre retourne `*this == _Code.category() && _Code.value() == _Errval`.  
  
##  <a name="a-nameerrorcategorymessagea--errorcategorymessage"></a><a name="error_category__message"></a>  error_category::message  
 Retourne le nom du code d’erreur spécifié.  
  
```
virtual string message(error_code::value_type val) const = 0;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`val`|Valeur de code d’erreur à décrire.|  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un nom descriptif du code d’erreur `val` pour la catégorie.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorcategorynamea--errorcategoryname"></a><a name="error_category__name"></a>  error_category::name  
 Retourne le nom de la catégorie.  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nom de la catégorie sous forme de chaîne d’octets terminée par un caractère null.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorcategoryoperatoreqeqa--errorcategoryoperator"></a><a name="error_category__operator_eq_eq"></a>  error_category::operator==  
 Vérifie l’égalité d’objets `error_category`.  
  
```
bool operator==(const error_category& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’égalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets sont égaux, **false** si les objets ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur membre retourne `this == &right`.  
  
##  <a name="a-nameerrorcategoryoperatorneqa--errorcategoryoperator"></a><a name="error_category__operator_neq"></a>  error_category::operator!=  
 Vérifie l’inégalité d’objets `error_category`.  
  
```
bool operator!=(const error_category& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’inégalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_category` n’est pas égal à l’objet `error_category` passé dans `right` ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `(!*this == right)`.  
  
##  <a name="a-nameerrorcategoryoperatorlta--errorcategoryoperatorlt"></a><a name="error_category__operator_lt_"></a>  error_category::operator&lt;  
 Vérifie si l’objet [error_category](../standard-library/error-category-class.md) est inférieur à l’objet `error_category` transmis pour la comparaison.  
  
```
bool operator<(const error_category& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet `error_category` à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_category` est inférieur à l’objet `error_category` transmis pour la comparaison ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `this < &right`.  
  
##  <a name="a-nameerrorcategoryvaluetypea--errorcategoryvaluetype"></a><a name="error_category__value_type"></a>  error_category::value_type  
 Type qui représente la valeur de code d’erreur stockée.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Notes  
 Cette définition de type est un synonyme de `int`.  
  
## <a name="see-also"></a>Voir aussi  
 [<system_error>](../standard-library/system-error.md)




