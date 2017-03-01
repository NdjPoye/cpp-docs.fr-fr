---
title: '&lt;system_error&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 43098f6f9276c9a66aaa7a30c95a6696e33f8429
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt;, fonctions
||||  
|-|-|-|  
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|  
|[system_category](#system_category)|  
  
##  <a name="a-namegenericcategorya--genericcategory"></a><a name="generic_category"></a>  generic_category  
 Représente la catégorie des erreurs génériques.  
  
```
extern const error_category& generic_category();
```  
  
### <a name="remarks"></a>Notes  
 L’objet `generic_categor`y est une implémentation de [error_category](../standard-library/error-category-class.md).  
  
##  <a name="a-namemakeerrorcodea--makeerrorcode"></a><a name="make_error_code"></a>  make_error_code  
 Crée un objet de code d’erreur.  
  
```
error_code make_error_code(generic_errno _Errno);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errno`|Valeur d’énumération à stocker dans l’objet de code d’erreur.|  
  
### <a name="return-value"></a>Valeur de retour  
 L’objet de code d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemakeerrorconditiona--makeerrorcondition"></a><a name="make_error_condition"></a>  make_error_condition  
 Crée un objet de condition d’erreur.  
  
```
error_condition make_error_condition(generic_errno _Errno);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Errno`|Valeur d’énumération à stocker dans l’objet de condition d’erreur.|  
  
### <a name="return-value"></a>Valeur de retour  
 L’objet de condition d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesystemcategorya--systemcategory"></a><a name="system_category"></a>  system_category  
 Représente la catégorie des erreurs provoquées par des dépassements de capacité du système de bas niveau.  
  
```
extern const error_category& system_category();
```  
  
### <a name="remarks"></a>Notes  
 L’objet `system_categor`y est une implémentation de [error_category](../standard-library/error-category-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [<system_error>](../standard-library/system-error.md)




