---
title: "Avertissement du compilateur (niveau&#160;1) C4952 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4952"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4952"
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4952
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : aucune donnée de profil trouvée dans la base de données 'pgd\_file' du programme  
  
 Lors de l’utilisation de [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un module d’entrée qui a été recompilé après `/LTCG:PGINSTRUMENT` et possède une nouvelle fonction \(***function***\)  
  
 Cet avertissement possède un caractère informatif. Pour résoudre cet avertissement, exécutez `/LTCG:PGINSTRUMENT`, relancez toutes les séries de tests, puis exécutez `/LTCG:PGOPTIMIZE`.  
  
 Si `/LTCG:PGOPTIMIZE` avait été utilisé, cet avertissement aurait été remplacé par une erreur.