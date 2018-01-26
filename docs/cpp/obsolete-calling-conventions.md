---
title: "Conventions d’appel obsolètes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs: C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad065eb3f35080ff2e5743c0259b20ba72ee6175
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="obsolete-calling-conventions"></a>Conventions d’appel obsolètes
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Le **__pascal**, **__fortran**, et **__syscall** conventions d’appel ne sont plus prises en charge. Vous pouvez émuler leurs fonctionnalités en utilisant l’une des conventions d’appel prises en charge et les options appropriées de l’Éditeur de liens.  
  
 \<Windows.h > prend désormais en charge la **WINAPI** (macro), ce qui se traduit par la convention d’appel appropriée pour la cible. Utilisez **WINAPI** où vous avez utilisé précédemment **PASCAL** ou **__far \__pascal**.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)