---
title: "C4746 d’avertissement du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f92bae0e75d9a09de874cd999c044e703b3f3171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4746"></a>C4746 d’avertissement du compilateur
accès volatile de '\<expression > » dépend : [iso &#124; ms] configuration ; envisagez d’utiliser des fonctions intrinsèques __iso_volatile_load/store.  
  
 C4746 est émis chaque fois qu’une variable volatile est accessible directement. Il vise à aider les développeurs à identifier les emplacements de code qui sont affectées par le modèle volatil spécifique actuellement spécifié (qui peuvent être contrôlé par le [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) option du compilateur). En particulier, il peut être utile pour la localisation des barrières de mémoire généré par le compilateur de matériel lorsque /volatile:ms est utilisé.  
  
 Les fonctions intrinsèques __iso_volatile_load/store peuvent être utilisés pour accéder explicitement les mémoire volatile sans être affecté par le modèle volatil. À l’aide de ces fonctions intrinsèques ne déclenche pas C4746.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.