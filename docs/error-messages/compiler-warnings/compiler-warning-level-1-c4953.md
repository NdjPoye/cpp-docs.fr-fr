---
title: "Avertissement du compilateur (niveau&#160;1) C4953 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4953"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4953"
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau&#160;1) C4953
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' Inline a été modifié depuis le rassemblement des données de profil ; données de profil non utilisées  
  
 Quand vous avez utilisé [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un module d’entrée qui a été recompilé après `/LTCG:PGINSTRUMENT` et qui possède une fonction \(***function***\) qui a été modifiée et dans laquelle des séries de tests existantes ont identifié la fonction comme candidate à l’incorporation \(inlining\). Toutefois, en raison de la recompilation du module, la fonction ne sera plus candidate à l’incorporation \(inlining\).  
  
 Cet avertissement possède un caractère informatif. Pour résoudre cet avertissement, exécutez `/LTCG:PGINSTRUMENT`, relancez toutes les séries de tests, puis exécutez `/LTCG:PGOPTIMIZE`.  
  
 Si `/LTCG:PGOPTIMIZE` avait été utilisé, cet avertissement aurait été remplacé par une erreur.