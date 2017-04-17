---
title: error_condition, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- std::error_condition
- error_condition
- std.error_condition
dev_langs:
- C++
helpviewer_keywords:
- error_condition class
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
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
ms.openlocfilehash: 4b9bc9b48c09c2b50b25eeb71a7fe9b5ad812157
ms.lasthandoff: 02/24/2017

---
# <a name="errorcondition-class"></a>error_condition, classe
Représente des codes d’erreur définis par l’utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>Notes  
 Un objet de type `error_condition` stocke une valeur de code d’erreur et un pointeur vers un objet qui représente une [catégorie](../standard-library/error-category-class.md) de codes d’erreur que vous utilisez pour signaler les erreurs définies par l’utilisateur.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[error_condition](#error_condition__error_condition)|Construit un objet de type `error_condition`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#error_condition__value_type)|Type qui représente la valeur de code d’erreur stockée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[assign](#error_condition__assign)|Assigne une valeur de code d’erreur et une catégorie à une condition d’erreur.|  
|[category](#error_condition__category)|Retourne la catégorie de l’erreur.|  
|[clear](#error_condition__clear)|Efface la valeur de code d’erreur et la catégorie.|  
|[message](#error_condition__message)|Retourne le nom du code d’erreur.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](#error_condition__operator_eq_eq)|Vérifie l’égalité d’objets `error_condition`.|  
|[operator!=](#error_condition__operator_neq)|Vérifie l’inégalité d’objets `error_condition`.|  
|[operator<](#error_condition__operator_lt_)|Vérifie si l’objet `error_condition` est inférieur à l’objet `error_code` transmis pour la comparaison.|  
|[operator=](#error_condition__operator_eq)|Assigne une nouvelle valeur d’énumération à l’objet `error_condition`.|  
|[operator bool](#error_condition__operator_bool)|Convertit une variable de type `error_condition`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameerrorconditionassigna--errorconditionassign"></a><a name="error_condition__assign"></a>  error_condition::assign  
 Assigne une valeur de code d’erreur et une catégorie à une condition d’erreur.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`val`|Valeur de code d’erreur à stocker dans `error_code`.|  
|`_Cat`|Catégorie d’erreur à stocker dans `error_code`.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre stocke `val` comme valeur de code d’erreur et un pointeur vers `_Cat`.  
  
##  <a name="a-nameerrorconditioncategorya--errorconditioncategory"></a><a name="error_condition__category"></a>  error_condition::category  
 Retourne la catégorie de l’erreur.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à la catégorie d’erreur stockée  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorconditioncleara--errorconditionclear"></a><a name="error_condition__clear"></a>  error_condition::clear  
 Efface la valeur de code d’erreur et la catégorie.  
  
```
clear();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre stocke une valeur de code d’erreur égale à zéro et un pointeur vers l’objet [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorconditionerrorconditiona--errorconditionerrorcondition"></a><a name="error_condition__error_condition"></a>  error_condition::error_condition  
 Construit un objet de type `error_condition`.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`val`|Valeur de code d’erreur à stocker dans `error_condition`.|  
|`_Cat`|Catégorie d’erreur à stocker dans `error_condition`.|  
|`_Errcode`|Valeur d’énumération à stocker dans `error_condition`.|  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur stocke une valeur de code d’erreur égale à zéro et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Le deuxième constructeur stocke `val` comme valeur de code d’erreur et un pointeur vers [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Le troisième constructeur stocke `(value_type)_Errcode` comme valeur de code d’erreur et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorconditionmessagea--errorconditionmessage"></a><a name="error_condition__message"></a>  error_condition::message  
 Retourne le nom du code d’erreur.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `string` représentant le nom du code d’erreur.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `category().message(value())`.  
  
##  <a name="a-nameerrorconditionoperatoreqeqa--errorconditionoperator"></a><a name="error_condition__operator_eq_eq"></a>  error_condition::operator==  
 Vérifie l’égalité d’objets `error_condition`.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’égalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets sont égaux ; **false** si les objets ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `category() == right.category() && value == right.value()`.  
  
##  <a name="a-nameerrorconditionoperatorneqa--errorconditionoperator"></a><a name="error_condition__operator_neq"></a>  error_condition::operator!=  
 Vérifie l’inégalité d’objets `error_condition`.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’inégalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_condition` n’est pas égal à l’objet `error_condition` passé dans `right` ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `!(*this == right)`.  
  
##  <a name="a-nameerrorconditionoperatorlta--errorconditionoperatorlt"></a><a name="error_condition__operator_lt_"></a>  error_condition::operator&lt;  
 Vérifie si l’objet `error_condition` est inférieur à l’objet `error_code` transmis pour la comparaison.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet `error_condition` à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_condition` est inférieur à l’objet `error_condition` transmis pour la comparaison ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="a-nameerrorconditionoperatoreqa--errorconditionoperator"></a><a name="error_condition__operator_eq"></a>  error_condition::operator=  
 Assigne une nouvelle valeur d’énumération à l’objet `error_condition`.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errcode`|Valeur d’énumération à assigner à l’objet `error_condition`.|  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet `error_condition` auquel la fonction membre assigne la nouvelle valeur d’énumération.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre stocke `(value_type)error` comme valeur de code d’erreur et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category). Il retourne `*this`.  
  
##  <a name="a-nameerrorconditionoperatorboola--errorconditionoperator-bool"></a><a name="error_condition__operator_bool"></a>  error_condition::operator bool  
 Convertit une variable de type `error_condition`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne de l’objet `error_condition`.  
  
### <a name="remarks"></a>Notes  
 L’opérateur retourne une valeur convertible en `true` uniquement si [value](#error_condition__value) n’est pas égal à zéro. Le type de retour est convertible uniquement en `bool` et non en `void *` ou en un autre type scalaire connu.  
  
##  <a name="a-nameerrorconditionvaluea--errorconditionvalue"></a><a name="error_condition__value"></a>  error_condition::value  
 Retourne la valeur de code d’erreur stockée.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de code d’erreur stockée de type [value_type](#error_condition__value_type).  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorconditionvaluetypea--errorconditionvaluetype"></a><a name="error_condition__value_type"></a>  error_condition::value_type  
 Type qui représente la valeur de code d’erreur stockée.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Notes  
 La définition de type est un synonyme de `int`.  
  
## <a name="see-also"></a>Voir aussi  
 [error_category, classe](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)



