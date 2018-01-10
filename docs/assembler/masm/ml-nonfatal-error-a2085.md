---
title: Erreur ML non fatale A2085 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f987b775c13b0e477fd5c1d215d556069535a0fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2085"></a>Erreur ML non fatale A2085
**instruction ou un Registre ne pas accepté dans le mode actuel du processeur**  
  
 Un utilisateur a tenté d’utiliser une instruction, un enregistrement ou un mot clé qui n’est pas valide pour le mode de processeur actuel.  
  
 Par exemple, les registres 32 bits requièrent [.386](../../assembler/masm/dot-386.md) ou version ultérieure. Les registres de contrôle telles que CR0 nécessitent le mode privilégié [.386P](../../assembler/masm/dot-386p.md) ou version ultérieure. Cette erreur est également générée pour le **NEAR32**, **FAR32**, et **plat** mots clés, qui le nécessitent. **386** ou version ultérieure.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)