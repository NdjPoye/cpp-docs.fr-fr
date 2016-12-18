---
title: "Erreur irr&#233;cup&#233;rable C1076 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1076"
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : la limite du tas interne a été atteinte ; utilisez \/Zm pour spécifier une limite plus élevée  
  
 Cette erreur peut être provoquée par un trop grand nombre de symboles, ou d'instanciations de modèles.  
  
 Pour corriger cette erreur :  
  
1.  Utilisez l'option [\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) pour définir la limite de mémoire du compilateur en fonction de la valeur spécifiée dans le message d'erreur [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md).  Pour plus d'informations sur la définition de cette valeur dans [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], consultez la section Remarques dans [\/Zm \(Spécifier la limite d'allocation mémoire d'en\-tête précompilé\)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  Si vous utilisez des compilateurs hébergés 32 bits sur un système d'exploitation 64 bits, utilisez les compilateurs hébergés 64 bits à la place.  Pour plus d'informations, consultez [Comment : activer un ensemble d'outils du compilateur Visual C\+\+ 64 bits sur la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Éliminez les fichiers include superflus.  
  
4.  Éliminez les variables globales non nécessaires, par exemple en allouant la mémoire de façon dynamique au lieu de déclarer un grand tableau.  
  
5.  Éliminez les déclarations non utilisées.  
  
6.  Fractionnez les grandes fonctions en fonctions plus petites.  
  
7.  Fractionnez les grandes classes en classes plus petites.  
  
8.  Fractionnez le fichier en cours en fichiers moins volumineux.  
  
 Si l'erreur C1076 apparaît immédiatement après le démarrage de la génération, la valeur spécifiée par **\/Zm** est sans doute trop élevée pour votre programme.  Réduisez la valeur **\/Zm**.