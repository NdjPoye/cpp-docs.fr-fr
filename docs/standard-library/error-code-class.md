---
title: error_code, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- error_code
- std.error_code
- std::error_code
- system_error/std::error_code
dev_langs:
- C++
helpviewer_keywords:
- error_code class
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
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
ms.openlocfilehash: 4959d72feaae22cb31a5bc7b6f6aa1b5f5b8be02
ms.lasthandoff: 02/24/2017

---
# <a name="errorcode-class"></a>error_code, classe
Représente les erreurs système de bas niveau spécifiques de l’implémentation.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class error_code;
```  
  
## <a name="remarks"></a>Notes  
 Un objet de type `error_code` stocke une valeur de code d’erreur et un pointeur vers un objet qui représente une [catégorie](../standard-library/error-category-class.md) de codes d’erreur décrivant les erreurs système de bas niveau signalées.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[error_code](#error_code__error_code)|Construit un objet de type `error_code`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#error_code__value_type)|Type qui représente la valeur de code d’erreur stockée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[assign](#error_code__assign)|Assigne une valeur de code d’erreur et une catégorie à un code d’erreur.|  
|[category](#error_code__category)|Retourne la catégorie de l’erreur.|  
|[clear](#error_code__clear)|Efface la valeur de code d’erreur et la catégorie.|  
|[default_error_condition](#error_code__default_error_condition)|Retourne la condition d’erreur par défaut.|  
|[message](#error_code__message)|Retourne le nom du code d’erreur.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](#error_code__operator_eq_eq)|Vérifie l’égalité d’objets `error_code`.|  
|[operator!=](#error_code__operator_neq)|Vérifie l’inégalité d’objets `error_code`.|  
|[operator<](#error_code__operator_lt_)|Vérifie si l’objet `error_code` est inférieur à l’objet `error_code` transmis pour la comparaison.|  
|[operator=](#error_code__operator_eq)|Assigne une nouvelle valeur d’énumération à l’objet `error_code`.|  
|[operator bool](#error_code__operator_bool)|Convertit une variable de type `error_code`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<system_error>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameerrorcodeassigna--errorcodeassign"></a><a name="error_code__assign"></a>  error_code::assign  
 Assigne une valeur de code d’erreur et une catégorie à un code d’erreur.  
  
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
  
##  <a name="a-nameerrorcodecategorya--errorcodecategory"></a><a name="error_code__category"></a>  error_code::category  
 Retourne la catégorie de l’erreur.  
  
```
const error_category& category() const;
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorcodecleara--errorcodeclear"></a><a name="error_code__clear"></a>  error_code::clear  
 Efface la valeur de code d’erreur et la catégorie.  
  
```
clear();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre stocke une valeur de code d’erreur égale à zéro et un pointeur vers l’objet [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorcodedefaulterrorconditiona--errorcodedefaulterrorcondition"></a><a name="error_code__default_error_condition"></a>  error_code::default_error_condition  
 Retourne la condition d’erreur par défaut.  
  
```
error_condition default_error_condition() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 [error_condition](../standard-library/error-condition-class.md) spécifié par [default_error_condition](../standard-library/error-category-class.md#error_category__default_error_condition).  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `category().default_error_condition(value())`.  
  
##  <a name="a-nameerrorcodeerrorcodea--errorcodeerrorcode"></a><a name="error_code__error_code"></a>  error_code::error_code  
 Construit un objet de type `error_code`.  
  
```
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`val`|Valeur de code d’erreur à stocker dans `error_code`.|  
|`_Cat`|Catégorie d’erreur à stocker dans `error_code`.|  
|`_Errcode`|Valeur d’énumération à stocker dans `error_code`.|  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur stocke une valeur de code d’erreur égale à zéro et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Le deuxième constructeur stocke `val` comme valeur de code d’erreur et un pointeur vers [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Le troisième constructeur stocke `(value_type)_Errcode` comme valeur de code d’erreur et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorcodemessagea--errorcodemessage"></a><a name="error_code__message"></a>  error_code::message  
 Retourne le nom du code d’erreur.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `string` représentant le nom du code d’erreur.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `category().message(value())`.  
  
##  <a name="a-nameerrorcodeoperatoreqeqa--errorcodeoperator"></a><a name="error_code__operator_eq_eq"></a>  error_code::operator==  
 Vérifie l’égalité d’objets `error_code`.  
  
```
bool operator==(const error_code& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’égalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les objets sont égaux ; **false** si les objets ne sont pas égaux.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `category() == right.category() && value == right.value()`.  
  
##  <a name="a-nameerrorcodeoperatorneqa--errorcodeoperator"></a><a name="error_code__operator_neq"></a>  error_code::operator!=  
 Vérifie l’inégalité d’objets `error_code`.  
  
```
bool operator!=(const error_code& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet dont l’inégalité doit être vérifiée.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_code` n’est pas égal à l’objet `error_code` passé dans `right` ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `!(*this == right)`.  
  
##  <a name="a-nameerrorcodeoperatorlta--errorcodeoperatorlt"></a><a name="error_code__operator_lt_"></a>  error_code::operator&lt;  
 Vérifie si l’objet [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) est inférieur à l’objet `error_code` transmis pour la comparaison.  
  
```
bool operator<(const error_code& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Objet error_code à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si l’objet `error_code` est inférieur à l’objet `error_code` transmis pour la comparaison ; sinon, **false**.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre retourne `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="a-nameerrorcodeoperatoreqa--errorcodeoperator"></a><a name="error_code__operator_eq"></a>  error_code::operator=  
 Assigne une nouvelle valeur d’énumération à l’objet [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31).  
  
```
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type&
 operator=(_Enum _Errcode);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errcode`|Valeur d’énumération à assigner à l’objet `error_code`.|  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet `error_code` auquel la fonction membre assigne la nouvelle valeur d’énumération.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre stocke `(value_type)_Errcode` comme valeur de code d’erreur et un pointeur vers [generic_category](../standard-library/system-error-functions.md#generic_category). Il retourne `*this`.  
  
##  <a name="a-nameerrorcodeoperatorboola--errorcodeoperator-bool"></a><a name="error_code__operator_bool"></a>  error_code::operator bool  
 Convertit une variable de type `error_code`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne de l’objet `error_code`.  
  
### <a name="remarks"></a>Notes  
 L’opérateur retourne une valeur convertible en `true` uniquement si [value](#error_code__value) n’est pas égal à zéro. Le type de retour est convertible uniquement en `bool` et non en `void *` ou en un autre type scalaire connu.  
  
##  <a name="a-nameerrorcodevaluea--errorcodevalue"></a><a name="error_code__value"></a>  error_code::value  
 Retourne la valeur de code d’erreur stockée.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de code d’erreur stockée de type [value_type](#error_code__value_type).  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameerrorcodevaluetypea--errorcodevaluetype"></a><a name="error_code__value_type"></a>  error_code::value_type  
 Type qui représente la valeur de code d’erreur stockée.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Notes  
 Cette définition de type est un synonyme de `int`.  
  
## <a name="see-also"></a>Voir aussi  
 [error_category, classe](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




