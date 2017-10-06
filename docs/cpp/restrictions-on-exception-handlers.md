---
title: "Restrictions sur les gestionnaires d’exceptions | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1806c737b9adfcefbe6417fda92ddc054094d4db
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="restrictions-on-exception-handlers"></a>Restrictions sur les gestionnaires d'exceptions
La limitation principale concernant l'utilisation des gestionnaires d'exceptions dans le code tient au fait que vous ne pouvez pas utiliser une instruction `goto` pour accéder à un bloc d'instruction `__try`. À la place, vous devez entrer dans le bloc d'instruction via le flux de contrôle normal. Vous pouvez effectuer un saut hors d'un bloc d'instruction `__try` et imbriquer des gestionnaires d'exceptions comme vous le souhaitez.  
  
## <a name="see-also"></a>Voir aussi  
 [L’écriture d’un gestionnaire d’exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
