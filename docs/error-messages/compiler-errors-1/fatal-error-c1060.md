---
title: "Erreur irrécupérable C1060 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c551ed3a6befbf646394929a6bcc6406ea93b19f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="fatal-error-c1060"></a>Erreur irrécupérable C1060
espace du tas insuffisant pour le compilateur  
  
 Le système d'exploitation ou la bibliothèque Runtime ne peut pas répondre à une demande de mémoire.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Pour corriger cette erreur, essayez les solutions possibles suivantes  
  
1.  Si le compilateur émet également les erreurs [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) et [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), utilisez le [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) option du compilateur afin de réduire la limite d’allocation de mémoire. Si vous réduisez l'allocation de mémoire restante, l'espace du tas dont dispose votre application est plus important.  
  
     Si le [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) option est déjà définie, essayez de le supprimer. Il se peut que l'espace du tas soit épuisé, car la limite d'allocation de mémoire spécifiée dans l'option est trop élevée. Le compilateur utilise une limite par défaut si vous supprimez le [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) option.  
  
2.  Si vous compilez sur une plateforme 64 bits, utilisez l'ensemble d'outils de compilateur 64 bits. Pour plus d’informations, consultez [Comment : activer un 64 bits Visual C++ ensemble d’outils de la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Sur Windows 32 bits, essayez d’utiliser le [/3 GB](http://go.microsoft.com/fwlink/p/?linkid=177831) commutateur boot.ini.  
  
4.  Augmentez la taille du fichier d'échange Windows.  
  
5.  Fermez les autres programmes en cours d'exécution.  
  
6.  Éliminez les fichiers include superflus.  
  
7.  Éliminez les variables globales inutiles, par exemple, en allouant la mémoire de façon dynamique au lieu de déclarer un grand tableau.  
  
8.  Éliminez les déclarations non utilisées.  
  
9. Fractionnez le fichier en cours en fichiers moins volumineux.