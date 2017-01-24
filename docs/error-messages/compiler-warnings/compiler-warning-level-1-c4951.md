---
title: "Avertissement du compilateur (niveau&#160;1) C4951 | Microsoft Docs"
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
  - "C4951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4951"
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' a été modifié depuis que les données de profil ont été regroupées ; données de profil de fonction non utilisées  
  
 Une fonction d’un module d’entrée a été remplacée par [\/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), de sorte que les données de profil ne sont plus valides. Le module d’entrée a été recompilé après **\/LTCG:PGINSTRUMENT** et a une fonction \(***function***\) avec un flux de contrôle différent de celui du module au moment de l’opération **\/LTCG:PGINSTRUMENT**.  
  
 Cet avertissement est à caractère informatif. Pour résoudre cet avertissement, exécutez **\/LTCG:PGINSTRUMENT**, relancez toutes les séries de tests, puis exécutez **\/LTCG:PGOPTIMIZE**.  
  
 Si **\/LTCG:PGOPTIMIZE** avait été utilisé, cet avertissement aurait été remplacé par une erreur.