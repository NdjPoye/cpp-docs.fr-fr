---
title: bad_exception, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1b332b4f76f24f873fd8a57d302fc2643a71f1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="badexception-class"></a>bad_exception, classe

La classe décrit une exception pouvant être levée à partir d’un gestionnaire d’exceptions inattendues.

## <a name="syntax"></a>Syntaxe

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Notes

[unexpected](../standard-library/exception-functions.md#unexpected) lève un `bad_exception` au lieu de terminer ou d’appeler une autre fonction spécifiée par [set_unexpected](../standard-library/exception-functions.md#set_unexpected) si `bad_exception` est inclus dans la liste d’exceptions levées d’une fonction.

La valeur retournée par **what** est une chaîne C définie par l’implémentation. Aucune des fonctions membres ne lève d'exception.

Pour obtenir la liste des membres hérités par la classe `bad_exception`, consultez [exception, classe](../standard-library/exception-class.md).

## <a name="example"></a>Exemple

Consultez [set_unexpected](../standard-library/exception-functions.md#set_unexpected) pour obtenir un exemple d’utilisation de la fonction [unexpected](../standard-library/exception-functions.md#unexpected) levant un `bad_exception`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<exception>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[exception, classe](../standard-library/exception-class.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
