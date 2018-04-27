---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89a027f9c31b9779991ebaee80b4e9d1a97d8ff7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Fournit une conversion implicite de `vector<bool>::reference` en `bool`.

## <a name="syntax"></a>Syntaxe

```cpp
operator bool() const;
```

## <a name="return-value"></a>Valeur de retour

La valeur booléenne de l’élément de l’objet [vector\<bool>](../standard-library/vector-bool-class.md).

## <a name="remarks"></a>Notes

L'objet `vector<bool>` ne peut pas être modifié par cet opérateur.

## <a name="requirements"></a>Spécifications

**En-tête :** \<vector>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[vecteur\<bool > :: classe de référence](../standard-library/vector-bool-reference-class.md)<br/>
[Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)<br/>
