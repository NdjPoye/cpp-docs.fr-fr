---
title: "Erreur irrécupérable C1076 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2e912cc4910ab1362719d94f374f145e90747e69
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1076"></a>Erreur irrécupérable C1076
limite du compilateur : la limite du tas interne a été atteinte ; utilisez /Zm pour spécifier une limite plus élevée  
  
 Cette erreur peut être provoquée par un trop grand nombre de symboles, ou d'instanciations de modèles.  
  
 Pour corriger cette erreur :  
  
1.  Utilisez le [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) option permettant de définir la limite de mémoire du compilateur pour la valeur spécifiée dans le [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) message d’erreur. Pour plus d’informations qui expliquent comment définir cette valeur dans [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], consultez la section Notes dans [/Zm (spécifier précompilés en-tête limite d’Allocation mémoire)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  Si vous utilisez des compilateurs hébergés 32 bits sur un système d'exploitation 64 bits, utilisez les compilateurs hébergés 64 bits à la place. Pour plus d’informations, consultez [Comment : activer un 64 bits Visual C++ ensemble d’outils de la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Éliminez les fichiers include superflus.  
  
4.  Éliminez les variables globales non nécessaires, par exemple en allouant la mémoire de façon dynamique au lieu de déclarer un grand tableau.  
  
5.  Éliminez les déclarations non utilisées.  
  
6.  Fractionnez les grandes fonctions en fonctions plus petites.  
  
7.  Fractionnez les grandes classes en classes plus petites.  
  
8.  Fractionnez le fichier en cours en fichiers moins volumineux.  
  
 Si l’erreur C1076 apparaît immédiatement après le démarrage de la build, la valeur spécifiée pour **/Zm** est sans doute trop élevée pour votre programme. Réduire le **/Zm** valeur.
