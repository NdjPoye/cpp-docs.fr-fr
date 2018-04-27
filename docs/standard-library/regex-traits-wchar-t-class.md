---
title: regex_traits&lt;wchar_t&gt;, classe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- regex/std::regex_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- regex_traits<wchar_t> class
ms.assetid: 288d6fdb-fb8e-4a4d-904a-53916be7f95b
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 19403ce75bd453754617167b2d6a26cc0a8deec8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="regextraitsltwchartgt-class"></a>regex_traits&lt;wchar_t&gt;, classe

Spécialisation de regex_traits pour wchar_t.

## <a name="syntax"></a>Syntaxe

```cpp
template <>
class regex_traits<wchar_t>
```

## <a name="remarks"></a>Notes

La classe est une spécialisation explicite de la classe de modèle [regex_traits](../standard-library/regex-traits-class.md) pour les éléments du type `wchar_t` (pour qu’elle puisse tirer parti des fonctions de bibliothèque qui manipulent des objets de ce type).

## <a name="requirements"></a>Spécifications

**En-tête :** \<regex>

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants, classe](../standard-library/regex-constants-class.md)<br/>
[regex_error, classe](../standard-library/regex-error-class.md)<br/>
[\<regex>, fonctions](../standard-library/regex-functions.md)<br/>
[regex_iterator, classe](../standard-library/regex-iterator-class.md)<br/>
[\<regex>, opérateurs](../standard-library/regex-operators.md)<br/>
[regex_token_iterator, classe](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits, classe](../standard-library/regex-traits-class.md)<br/>
[\<regex>, typedefs](../standard-library/regex-typedefs.md)<br/>
