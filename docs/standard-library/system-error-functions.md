---
title: '&lt;system_error&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 6135a3dc51b372c85545f01f52c70cbc6f236e64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt;, fonctions

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

Représente la catégorie des erreurs génériques.

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>Notes

Le `generic_category` objet est une implémentation de [error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a>  make_error_code

Crée un objet de code d’erreur.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`_Errno`|Valeur d’énumération à stocker dans l’objet de code d’erreur.|

### <a name="return-value"></a>Valeur de retour

L’objet de code d’erreur.

### <a name="remarks"></a>Notes

## <a name="make_error_condition"></a>  make_error_condition

Crée un objet de condition d’erreur.

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>Paramètres

|Paramètre|Description|
|---------------|-----------------|
|`_Errno`|Valeur d’énumération à stocker dans l’objet de condition d’erreur.|

### <a name="return-value"></a>Valeur de retour

L’objet de condition d’erreur.

### <a name="remarks"></a>Notes

## <a name="system_category"></a>  system_category

Représente la catégorie des erreurs provoquées par des dépassements de capacité du système de bas niveau.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Notes

Le `system_category` objet est une implémentation de [error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Voir aussi

[<system_error>](../standard-library/system-error.md)<br/>
