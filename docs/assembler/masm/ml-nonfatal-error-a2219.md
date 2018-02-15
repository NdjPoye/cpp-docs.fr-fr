---
title: Erreur ML non fatale A2219 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2219
dev_langs:
- C++
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4d683a51930c9a34b3bdae016b5d15c1401787a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2219"></a>Erreur ML non fatale A2219
**Alignement incorrect pour le décalage de code de déroulement**  
  
 L’opérande de [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md) et [. SAVEREG](../../assembler/masm/dot-savereg.md) doit être un multiple de 8.  L’opérande de [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md) et [. SETFRAME](../../assembler/masm/dot-setframe.md) doit être un multiple de 16.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)