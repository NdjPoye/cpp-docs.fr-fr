---
title: Erreur ML non fatale A2050 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 887a18ee274b3e09624a07e214f235333e2a9665
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2050"></a>Erreur ML non fatale A2050
**réel ou numéro BCD non autorisé**  
  
 Un nombre (réel) à virgule flottante ou la constante de binary coded decimal (BCD) a été utilisée autre que comme un initialiseur de données.  
  
 Une des conditions suivantes s’est produite :  
  
-   Un nombre réel ou un BCD a été utilisée dans une expression.  
  
-   Un nombre réel a été utilisé pour initialiser une directive autre que [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), ou [to](../../assembler/masm/tbyte.md).  
  
-   Un BCD a été utilisé pour initialiser une directive autre que `TBYTE`.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)