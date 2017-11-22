---
title: error_category, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
dev_langs:
- C++
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3e1b51db369a5f36b4c7428083d7dde4728642c3
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

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
|[value_type](#value_type)|Type qui représente la valeur de code d’erreur stockée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[default_error_condition](#default_error_condition)|Stocke la valeur de code d’erreur d’un objet de condition d’erreur.|  
|[equivalent](#equivalent)|Retourne une valeur qui spécifie si les objets d’erreur sont équivalents.|  
|[message](#message)|Retourne le nom du code d’erreur spécifié.|  
|[name](#name)|Retourne le nom de la catégorie.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|Vérifie l’égalité d’objets `error_category`.|  
|[operator!=](#op_neq)|Vérifie l’inégalité d’objets `error_category`.|  
|[operator<](#op_lt)|Vérifie si l’objet [error_category](../standard-library/error-category-class.md) est inférieur à l’objet `error_category` transmis pour la comparaison.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
##  <a name="default_error_condition"></a>  error_category::default_error_condition  
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
  
##  <a name="equivalent"></a>  error_category::equivalent  
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
  
##  <a name="message"></a>  error_category::message  
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
  
##  <a name="name"></a>  error_category::name  
 Retourne le nom de la catégorie.  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nom de la catégorie sous forme de chaîne d’octets terminée par un caractère null.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="op_eq_eq"></a>  error_category::operator==  
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
  
##  <a name="op_neq"></a>  error_category::operator!=  
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
  
##  <a name="op_lt"></a>  error_category::operator&lt;  
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
  
##  <a name="value_type"></a>  error_category::value_type  
 Type qui représente la valeur de code d’erreur stockée.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Notes  
 Cette définition de type est un synonyme de `int`.  
  
## <a name="see-also"></a>Voir aussi  
 [<system_error>](../standard-library/system-error.md)



