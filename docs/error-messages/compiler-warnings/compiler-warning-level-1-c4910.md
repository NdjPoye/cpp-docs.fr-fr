---
title: Compilateur avertissement (niveau 1) C4910 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8416e456a7d985eb7a3c40addb716ba5c30bf96
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4910"></a>Avertissement du compilateur (niveau 1) C4910
'\<identificateur >' : '__declspec (dllexport)' et 'extern' sont incompatibles sur une instanciation explicite  
  
 L’instanciation de modèle explicite nommée *\<identificateur >* est modifié à la fois par le `__declspec(dllexport)` et `extern` mots clés. Toutefois, ces mots clés s’excluent mutuellement. Le mot clé `__declspec(dllexport)` signifie que la classe de modèle doit être instanciée, tandis que le mot clé `extern` signifie que la classe de modèle ne doit pas être instanciée automatiquement.  
  
## <a name="see-also"></a>Voir aussi  
 [Instanciation explicite](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Règles générales et limitations](../../cpp/general-rules-and-limitations.md)
