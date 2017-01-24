---
title: "PogoSafeMode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PogoSafeMode"
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PogoSafeMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifiez s'il faut utiliser le mode rapide ou le mode sans échec pour le profilage d'application.  
  
## Syntaxe  
  
```  
PogoSafeMode  
```  
  
## Notes  
 L'optimisation guidée par profil \(PGO\) a deux modes possibles pendant la phase de profilage: mode rapide et mode sans échec.  Lorsque le profilage est en mode rapide, il utilise l'instruction **INC** pour incrémenter des compteurs de données.  L'instruction **INC** est plus rapide mais n'est pas thread\-safe.  Lorsque le profilage est en mode sans échec, il utilise l'instruction **LOCK INC** pour incrémenter des compteurs de données.  L'instruction **LOCK INC** a les mêmes fonctionnalités que l'instruction **INC**. Elle est thread\-safe mais est plus lente que l'instruction **INC**.  
  
 Par défaut, le profilage PGO fonctionne en mode rapide.  `PogoSafeMode` est obligatoire uniquement si vous souhaitez utiliser le mode sans échec.  
  
 Pour exécuter le profilage PGO en mode sans échec, vous devez soit utiliser la variable d'environnement `PogoSafeMode`, soit l'éditeur de liens **\-PogoSafeMode**, selon le système.  Si vous exécutez le profilage sur un ordinateur x64, vous devez utiliser le commutateur de l'Éditeur de liens.  Si vous exécutez le profilage sur un ordinateur x86, vous devez définir la variable d'environnement sur n'importe quelle valeur avant de démarrer le processus d'optimisation.  
  
## Exemple  
  
```  
set PogoSafeMode=1  
```  
  
## Voir aussi  
 [Variables d'environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)