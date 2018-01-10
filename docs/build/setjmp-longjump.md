---
title: setjmp-longjump | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 744b855d1b867507b54973f17e2a4f98b63e2b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
Lorsque vous incluez setjmpex.h ou setjmp.h, tous les appels à [setjmp](../c-runtime-library/reference/setjmp.md) ou [longjmp](../c-runtime-library/reference/longjmp.md) entraînent un déroulement qui appelle des destructeurs et enfin des appels.  Cela diffère de x86, y compris les résultats de setjmp.h dans les clauses finally et destructeurs ne pas appelés.  
  
 Un appel à `setjmp` conserve le pointeur de pile actuel, les registres non volatils et les registres MxCsr.  Les appels à `longjmp` retour à la plus récente `setjmp` appeler le site et réinitialise le pointeur de pile, les registres non volatils et MxCsr inscrit, à l’état préservé par la plus récente `setjmp` appeler.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)