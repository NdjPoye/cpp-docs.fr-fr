---
title: char_traits&lt;wchar_t&gt;, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2b20b72bf92679395b19b2ad6b8ae68143bb6d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="chartraitsltwchartgt-struct"></a>char_traits&lt;wchar_t&gt;, struct

Classe qui est une spécialisation du struct de modèle **char_traits\<CharType>** sur un élément de type `wchar_t`.

## <a name="syntax"></a>Syntaxe

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Notes

La spécialisation permet au struct de tirer parti des fonctions de bibliothèque qui manipulent les objets du type `wchar_t`.

## <a name="requirements"></a>Spécifications

**En-tête :** \<string>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[char_traits, struct](../standard-library/char-traits-struct.md)<br/>
[Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
