---
title: "Optimisation de l’Assembly Inline | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21f6954ece6adcc60fbb3a8620dd427e7c21042a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-inline-assembly"></a>Optimisation de l'assembly inline
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 La présence d'un bloc `__asm` dans une fonction affecte l'optimisation de plusieurs façons. D'abord, le compilateur ne tente pas d'optimiser le bloc `__asm` lui-même. Ce que vous écrivez dans le langage assembleur est exactement ce que vous obtenez. Ensuite, la présence d'un bloc `__asm` affecte le stockage des variables du registre. Le compilateur évite d'enregistrer les variables dans un bloc `__asm` si le contenu du registre est modifié par le bloc `__asm`. Enfin, certaines optimisations au niveau de la fonction seront affectées par l'inclusion du langage assembleur dans une fonction.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)