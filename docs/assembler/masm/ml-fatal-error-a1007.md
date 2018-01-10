---
title: "Erreur ML irrécupérable A1007 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1007
dev_langs: C++
helpviewer_keywords: A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 619f1eae458b52eb7851118d6702dccec769a1ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-fatal-error-a1007"></a>Erreur ML irrécupérable A1007
**niveau d’imbrication trop profond**  
  
 L’assembleur atteint sa limite d’imbrication. La limite est de 20 niveaux sauf indication contraire dans le cas contraire.  
  
 Une des conditions suivantes a été imbriquée trop profondément :  
  
-   Une directive de haut niveau tels que [. IF](../../assembler/masm/dot-if.md), [. RÉPÉTEZ les](../../assembler/masm/dot-repeat.md), ou [. Alors que](../../assembler/masm/dot-while.md).  
  
-   Une définition de structure.  
  
-   Une directive conditionnelle de l’assembly.  
  
-   Une définition de procédure.  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md) directive (la limite est 10).  
  
-   Une définition de segment.  
  
-   Un fichier include.  
  
-   Une macro.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)