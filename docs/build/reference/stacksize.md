---
title: STACKSIZE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STACKSIZE
dev_langs: C++
helpviewer_keywords: STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82b33d217e593a35b66bb3530840a739e93082ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="stacksize"></a>STACKSIZE
Définit la taille de la pile, en octets.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>Remarques  
 Pour définir la pile d’une manière équivalente est avec le [Allocations de la pile](../../build/reference/stack-stack-allocations.md) (/Stack) option. Consultez la documentation sur cette option pour plus d’informations la *réserver* et `commit` arguments.  
  
 Cette option a aucun effet sur les DLL.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)