---
title: STACKSIZE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9c09bea88c4f9452d0fab9371c8b9af8011fd32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stacksize"></a>STACKSIZE
Définit la taille de la pile, en octets.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>Notes  
 Pour définir la pile d’une manière équivalente est avec le [Allocations de la pile](../../build/reference/stack-stack-allocations.md) (/Stack) option. Consultez la documentation sur cette option pour plus d’informations la *réserver* et `commit` arguments.  
  
 Cette option a aucun effet sur les DLL.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)