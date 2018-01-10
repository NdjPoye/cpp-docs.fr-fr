---
title: "Erreur ML irrécupérable A1010 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1010
dev_langs: C++
helpviewer_keywords: A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b495fc2b8bd0e667dd7dae7e23347f6971ec4d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-fatal-error-a1010"></a>Erreur ML irrécupérable A1010
**imbrication de blocs non appariées :**  
  
 Un début du bloc ne disposait pas d’end correspondant, ou une fin de bloc n’a pas d’un début correspondant. Un des éléments suivants peut-être être concerné :  
  
-   Une directive de haut niveau tels que [. IF](../../assembler/masm/dot-if.md), [. RÉPÉTEZ les](../../assembler/masm/dot-repeat.md), ou [. Alors que](../../assembler/masm/dot-while.md).  
  
-   Une directive conditionnelle de l’assembly comme [IF](../../assembler/masm/if-masm.md), [RÉPÉTEZ](../../assembler/masm/repeat.md), ou **tandis que**.  
  
-   Une définition de structure ou union.  
  
-   Une définition de procédure.  
  
-   Une définition de segment.  
  
-   A [POPCONTEXT](../../assembler/masm/popcontext.md) la directive.  
  
-   Un assembly de conditionnelle directive comme une [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), ou **ENDIF** sans une correspondance [IF](../../assembler/masm/if-masm.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)