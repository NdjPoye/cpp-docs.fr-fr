---
title: time_put_byname, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34ac10a6456c2bc1b69d3076e5b3ba351507c3ee
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="timeputbyname-class"></a>time_put_byname, classe

La classe de modèle dérivée décrit un objet pouvant servir de facette de paramètres régionaux du type `time_put`\< CharType, OutputIterator >.

## <a name="syntax"></a>Syntaxe

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>Paramètres

`_Locname` Un nom de paramètres régionaux.

`_Refs` Un décompte de références initial.

## <a name="remarks"></a>Notes

Son comportement est déterminé par les paramètres régionaux [nommés](../standard-library/locale-class.md#name) `_Locname`. Chaque constructeur initialise son objet de base avec [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator>( `_Refs`).

## <a name="requirements"></a>Spécifications

**En-tête :** \<locale>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
