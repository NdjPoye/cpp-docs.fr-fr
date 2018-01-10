---
title: stdext, espace de noms | Microsoft Docs
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdext
dev_langs: C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59da07c0cea58e9fc4b544b9f3bad937b2951f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stdext-namespace"></a>stdext, espace de noms

Membres de la [ \<hash_map >](../standard-library/hash-map.md) et [ \<hash_set >](../standard-library/hash-set.md) fichiers d’en-tête ne sont pas actuellement partie de la norme ISO C++. Par conséquent, ces types et ces membres ont été déplacés de l’espace de noms `std` vers l’espace de noms `stdext`, de façon à rester conforme à la norme C++.

Lors de la compilation avec [/Ze](../build/reference/za-ze-disable-language-extensions.md), qui est la valeur par défaut, le compilateur vous avertit sur l’utilisation de `std` pour les membres de la \<hash_map > et \<hash_set > fichiers d’en-tête. Pour désactiver l’avertissement, utilisez le pragma [warning](../preprocessor/warning.md) .

Pour que le compilateur génère une erreur pour l’utilisation de `std` pour les membres de la \<hash_map > et \<hash_set > avec les fichiers d’en-tête **/Ze**, ajoutez la directive suivante avant de vous `#include` tous les fichiers d’en-tête de bibliothèque C++ Standard.

```cpp  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  

Lors de la compilation avec **/Za**, le compilateur génère une erreur.  

## <a name="see-also"></a>Voir aussi

[Vue d’ensemble de la bibliothèque standard C++](../standard-library/cpp-standard-library-overview.md)

