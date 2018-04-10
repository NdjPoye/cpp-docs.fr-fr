---
title: Erreur ML non fatale A2085 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29d0d58e5cd65c16c848b3cc05e10b9f57488639
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2085"></a>Erreur ML non fatale A2085
**instruction ou un Registre ne pas accepté dans le mode actuel du processeur**  
  
 Un utilisateur a tenté d’utiliser une instruction, un enregistrement ou un mot clé qui n’est pas valide pour le mode de processeur actuel.  
  
 Par exemple, les registres 32 bits requièrent [.386](../../assembler/masm/dot-386.md) ou version ultérieure. Les registres de contrôle telles que CR0 nécessitent le mode privilégié [.386P](../../assembler/masm/dot-386p.md) ou version ultérieure. Cette erreur est également générée pour le **NEAR32**, **FAR32**, et **plat** mots clés, qui le nécessitent. **386** ou version ultérieure.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)