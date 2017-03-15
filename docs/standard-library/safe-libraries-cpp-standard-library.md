---
title: "Bibliothèques sécurisées : bibliothèque standard C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 704101f267c1d63ffc5def918f031bfc9b257e67
ms.lasthandoff: 02/24/2017

---
# <a name="safe-libraries-c-standard-library"></a>Bibliothèques sécurisées : bibliothèque standard C++
Plusieurs améliorations ont été apportées aux bibliothèques fournies avec Visual C++, notamment la bibliothèque standard C++, pour les rendre plus sécurisées.  
  
 Plusieurs méthodes de la bibliothèque standard C++ ont été identifiés comme potentiellement dangereuses, car elles peuvent entraîner un dépassement de mémoire tampon ou d’autre défauts dans le code. L’utilisation de ces méthodes est déconseillée : de nouvelles méthodes plus sécurisées des méthodes ont été créées pour les remplacer. Ces nouvelles méthodes se trouvent toutes dans `_s`.  
  
 Plusieurs améliorations ont également été apportées pour renforcer la sécurité des itérateurs et des algorithmes. Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md), [Prise en charge des itérateurs de débogage](../standard-library/debug-iterator-support.md) et [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Notes  
 Le tableau suivant répertorie les méthodes de la bibliothèque C++ standard qui sont potentiellement dangereuses, ainsi que leur équivalent plus sécurisé :  
  
|Méthode potentiellement dangereuse|Équivalent plus sécurisé|  
|-------------------------------|----------------------|  
|[basic_string::copy](../standard-library/basic-string-class.md#basic_string__copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#basic_string___copy_s)|  
|[char_traits::copy](../standard-library/char-traits-struct.md#char_traits__copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#char_traits___copy_s)|  
  
 Si vous appelez une des méthodes potentiellement dangereuses ci-dessus, ou si vous utilisez incorrectement des itérateurs, le compilateur génère l’[avertissement du compilateur (niveau 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Pour plus d’informations sur la désactivation de ces avertissements, consultez [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Itérateurs vérifiés](../standard-library/checked-iterators.md)  
  
 [Prise en charge des itérateurs de débogage](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la bibliothèque C++ Standard](../standard-library/cpp-standard-library-overview.md)


