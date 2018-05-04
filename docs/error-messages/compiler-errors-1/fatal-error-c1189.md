---
title: Erreur irrécupérable C1189 | Documents Microsoft
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b49f227b5fda20ab0ba202d3d7eca99492509b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="fatal-error-c1189"></a>Erreur irrécupérable C1189

> **\#Erreur :** *message d’erreur fourni par l’utilisateur*

## <a name="remarks"></a>Notes

L’erreur C1189 est générée par le `#error` la directive. Le développeur qui code la directive spécifie le texte du message d’erreur. Pour plus d’informations, consultez [#error Directive (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Exemple

L’exemple suivant génère l’erreur C1189. Dans l’exemple, le développeur émet un message d’erreur personnalisé, car le `_WIN32` identificateur n’est pas défini :

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Voir aussi

[#define, directive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)