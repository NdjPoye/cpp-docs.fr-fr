---
title: Erreur du compilateur C3888 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
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
ms.openlocfilehash: 4b85385c97f5873c1b370cd72f0866439263f787
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3888"></a>Erreur du compilateur C3888
'name' : l’expression const associée à cette donnée membre littérale n’est pas prise en charge par C++/CLI  
  
 Le *nom* membre de données qui est déclaré avec le [littéral](../../windows/literal-cpp-component-extensions.md) mot clé est initialisé avec une valeur, le compilateur ne prend pas en charge. Le compilateur prend en charge uniquement les types constant, integral, enum et string. Il est probable que l’erreur **C3888** soit causée par l’utilisation d’un tableau d’octets pour l’initialisation de la donnée membre.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Vérifiez que le type de la donnée membre littérale déclarée est pris en charge.  
  
## <a name="see-also"></a>Voir aussi  
 [littéral](../../windows/literal-cpp-component-extensions.md)
