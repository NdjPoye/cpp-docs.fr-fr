---
title: "Erreur ML irrécupérable A1011 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3a614bc56c76b220eeeb73ce2cc7e90a9ca9b8e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1011"></a>Erreur ML irrécupérable A1011
**la directive doit être dans un bloc de contrôle**  
  
 L’assembleur trouvé une directive de haut niveau dans lequel une n’était pas attendue. Des directives suivantes ont été trouvés :  
  
-   [. AUTRE](../../assembler/masm/dot-else.md) sans [. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDIF](../../assembler/masm/dot-endif.md) sans [. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDW](../../assembler/masm/dot-endw.md) sans [. WHILE](../../assembler/masm/dot-while.md)  
  
-   [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) sans [. RÉPÉTEZ L’OPÉRATION](../../assembler/masm/dot-repeat.md)  
  
-   [. CONTINUER](../../assembler/masm/dot-continue.md) sans [. Alors que](../../assembler/masm/dot-while.md) ou [. RÉPÉTEZ L’OPÉRATION](../../assembler/masm/dot-repeat.md)  
  
-   [. ARRÊTER](../../assembler/masm/dot-break.md) sans [. Alors que](../../assembler/masm/dot-while.md) ou [. RÉPÉTEZ L’OPÉRATION](../../assembler/masm/dot-repeat.md)  
  
-   [. AUTRE](../../assembler/masm/dot-else.md) suivant `.ELSE`  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)