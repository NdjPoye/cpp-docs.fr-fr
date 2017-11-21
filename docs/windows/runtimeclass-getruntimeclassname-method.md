---
title: "Runtimeclass::getruntimeclassname, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
dev_langs: C++
helpviewer_keywords: GetRuntimeClassName method
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c82a3ae65ae65dfe43cb0ed645f802161f7a17f6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="runtimeclassgetruntimeclassname-method"></a>RuntimeClass::GetRuntimeClassName, méthode

Obtient le nom de la classe runtime de l’objet RuntimeClass actuel.

## <a name="syntax"></a>Syntaxe

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Paramètres

*runtimeName*  
Lorsque cette opération est terminée, le nom de la classe runtime.

## <a name="return-value"></a>Valeur de retour

S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.

## <a name="remarks"></a>Remarques

Une erreur d’assertion est émis if, #95 ; &#95; WRL_STRICT &#95; &#95; ou &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; &#95; n’est pas définie.

## <a name="requirements"></a>Spécifications

**En-tête :** implements.h

**Espace de noms :** Microsoft::WRL

## <a name="see-also"></a>Voir aussi

[RuntimeClass, classe](../windows/runtimeclass-class.md)