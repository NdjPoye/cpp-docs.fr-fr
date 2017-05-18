---
title: stdext, espace de noms | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 213b760a134a645a0b6552e4c3600fc4762b0bb2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="stdext-namespace"></a>Espace de noms stdext
Les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne font pas partie de la norme C++ ISO. Par conséquent, ces types et ces membres ont été déplacés de l’espace de noms `std` vers l’espace de noms `stdext`, de façon à rester conforme à la norme C++.  
  
 Lors de la compilation avec [/Ze](../build/reference/za-ze-disable-language-extensions.md), qui est la valeur par défaut, le compilateur vous avertit de l’utilisation de `std` pour les membres des fichiers d’en-tête <hash_map> et <hash_set>. Pour désactiver l’avertissement, utilisez le pragma [warning](../preprocessor/warning.md).  
  
 Pour que le compilateur génère une erreur pour l’utilisation de `std` pour les membres des fichiers d’entête <hash_map> et <hash_set> avec **/Ze**, ajoutez la directive suivante avant d’inclure des fichiers d’en-tête de la bibliothèque standard C++.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 Lors de la compilation avec **/Za**, le compilateur génère une erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la bibliothèque C++ Standard](../standard-library/cpp-standard-library-overview.md)


