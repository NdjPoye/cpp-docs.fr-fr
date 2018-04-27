---
title: char_traits&lt;char32_t&gt;, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed195f6ed4d1319d079a58f736c65a03e397bd1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltchar32tgt-struct"></a>char_traits&lt;char32_t&gt;, struct

Struct qui est une spécialisation du struct de modèle **char_traits\<CharType>** sur un élément de type `char32_t`.

## <a name="syntax"></a>Syntaxe

```cpp
template <>
struct char_traits<char32_t>;
```

## <a name="remarks"></a>Notes

La spécialisation permet au struct de tirer parti des fonctions de bibliothèque qui manipulent les objets du type `char32_t`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<string>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[\<string>](../standard-library/string.md)<br/>
[char_traits, struct](../standard-library/char-traits-struct.md)<br/>
