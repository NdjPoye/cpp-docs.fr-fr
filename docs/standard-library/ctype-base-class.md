---
title: ctype_base, classe| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- locale/std::ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb1bed10d9dbeb1ce508f1d0c1507e1c2a4bacf7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ctypebase-class"></a>ctype_base, classe

La classe sert de classe de base pour les facettes de la classe de modèle [ctype](../standard-library/ctype-class.md). Classe de base de la classe ctype utilisée pour définir des types énumération utilisés pour classifier ou tester les caractères, individuellement ou dans des plages entières.

## <a name="syntax"></a>Syntaxe

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>Notes

Elle définit un masque d’énumération. Chaque constante d’énumération caractérise une méthode de classification des caractères, comme défini par les fonctions avec des noms similaires déclarées dans l’en-tête \<ctype.h>. Les constantes sont :

- **space** (fonction [isspace](../standard-library/locale-functions.md#isspace))

- **print** (fonction [isprint](../standard-library/locale-functions.md#isprint))

- **cntrl** (fonction [iscntrl](../standard-library/locale-functions.md#iscntrl))

- **upper** (fonction [isupper](../standard-library/locale-functions.md#isupper))

- **lower** (fonction [islower](../standard-library/locale-functions.md#islower))

- **digit** (fonction [isdigit](../standard-library/locale-functions.md#isdigit))

- **punct** (fonction [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (fonction [isxdigit](../standard-library/locale-functions.md#isxdigit))

- **alpha** (fonction [isalpha](../standard-library/locale-functions.md#isalpha))

- **alnum** (fonction [isalnum](../standard-library/locale-functions.md#isalnum))

- **graph** (fonction [isgraph](../standard-library/locale-functions.md#isgraph))

Vous pouvez caractériser une combinaison de classifications en reliant ces constantes par une opération OR. En particulier, il est toujours true qui **à "alnum"** == ( **alpha** &#124; **chiffre** \) et **graphique** \= \= \( **à "alnum"** &#124; **punct**).

## <a name="requirements"></a>Spécifications

**En-tête :** \<locale>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
