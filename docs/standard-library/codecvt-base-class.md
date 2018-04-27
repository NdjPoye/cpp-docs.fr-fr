---
title: codecvt_base, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fbe4d0c6789ada5979359d0498b95350c5ba0c3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="codecvtbase-class"></a>codecvt_base, classe

Classe de base de la classe codecvt utilisée pour définir un type d’énumération appelé **result**, utilisé comme type de retour pour les fonctions membres de la classe facet afin d’indiquer le résultat d’une conversion.

## <a name="syntax"></a>Syntaxe

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Notes

Cette classe décrit une énumération commune à toutes les spécialisations de la classe de modèle [codecvt](../standard-library/codecvt-class.md). Le résultat de l’énumération décrit les valeurs de retour possibles de [do_in](../standard-library/codecvt-class.md#do_in) ou [do_out](../standard-library/codecvt-class.md#do_out) :

- **ok** si la conversion entre les codages de caractère internes et externes réussit.

- **partial** si la destination n’est pas assez grande pour que la conversion réussisse.

- **error** si la séquence source est incorrecte.

- **noconv** si la fonction n’exécute aucune conversion.

## <a name="requirements"></a>Spécifications

**En-tête :** \<locale>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
