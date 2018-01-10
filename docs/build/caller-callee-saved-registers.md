---
title: "Registres enregistrés des appelants-appelés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 61e8d57c177ded8102f257cf84adedc0de0e312a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="callercallee-saved-registers"></a>Registres enregistrés des appelants/appelés
Les registres RAX, RCX, RDX, R8, R9, R10, R11 sont considérés comme volatile et doit être considérée comme détruits sur les appels de fonction (sauf dans le cas contraire sécurité estimer par analyse telles qu’une optimisation de l’ensemble du programme).  
  
 Les registres RBX, RBP, RDI, RSI, RSP, R12, R13, R14 et R15 sont considérés comme non volatile et doivent être enregistrés et restauré par une fonction qui les utilise.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)