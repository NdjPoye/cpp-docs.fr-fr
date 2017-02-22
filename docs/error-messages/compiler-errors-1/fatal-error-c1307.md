---
title: "Erreur irr&#233;cup&#233;rable C1307 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1307"
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur irr&#233;cup&#233;rable C1307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le programme a été modifié depuis que les données du profil ont été recueillies  
  
 Lors de l'utilisation de [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), l'éditeur de liens a détecté un module d'entrée qui a été recompilé après \/LTCG:PGINSTRUMENT et qui a été modifié au point où les données de profil existantes ne sont plus pertinentes.  Par exemple, si le graphique des appels a été modifié dans le module recompilé, le compilateur génère l'erreur C1307.  
  
 Pour résoudre cette erreur, exécutez \/LTCG:PGINSTRUMENT, réalisez à nouveau toutes les séries de tests et exécutez \/LTCG:PGOPTIMIZE.  Si vous ne pouvez pas exécuter \/LTCG:PGINSTRUMENT et réaliser à nouveau toutes les séries de tests, utilisez \/LTCG:PGUPDATE au lieu de \/LTCG:PGOPTIMIZE pour créer l'image optimisée.