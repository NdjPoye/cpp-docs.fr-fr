---
title: Erreur ML non fatale A2133 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adc1929f14b5264717936f1a4aebb8dabd2e439d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2133"></a>Erreur ML non fatale A2133
**remplacé par INVOKE de valeur de Registre**  
  
 Un Registre a été passé comme argument à une procédure, mais le code généré par [INVOKE](../../assembler/masm/invoke.md) pour passer des autres arguments détruit le contenu du Registre.  
  
 Les registres AX, AL, AH, EAX, DX, DL, Diffie-Hellman et EDX peuvent être utilisés par l’assembleur pour effectuer la conversion de données.  
  
 Utilisez un autre registre.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)