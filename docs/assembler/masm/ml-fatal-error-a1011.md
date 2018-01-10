---
title: "Erreur ML irrécupérable A1011 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1011
dev_langs: C++
helpviewer_keywords: A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 470340e76897394e5b8ecb042ff97562b0c94c2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
-   [. AUTRE](../../assembler/masm/dot-else.md) suivant`.ELSE`  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)