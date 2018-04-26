---
title: time_base, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2bb249399d844aec74e53b12b9db046a2783a6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="timebase-class"></a>time_base, classe

La classe sert de classe de base pour les facettes de la classe de modèle time_get, définissant simplement le type énuméré **dateorder** et plusieurs constantes de ce type.

## <a name="syntax"></a>Syntaxe

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```

## <a name="remarks"></a>Notes

Chaque constante caractérise une manière différente d’ordonner les composants d’une date. Les constantes sont :

- **no_order** ne spécifie aucun ordre particulier.

- **dmy** spécifie l’ordre jour, mois, année, comme dans 2 décembre 1979.

- **mdy** spécifie l’ordre mois, jour, année, comme dans décembre 2, 1979.

- **ymd** spécifie l’ordre année, mois, jour, comme dans 1979/12/2.

- **ydm** spécifie l’ordre année, jour, mois, comme dans 1979: 2 déc.

## <a name="requirements"></a>Spécifications

**En-tête :** \<locale>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
