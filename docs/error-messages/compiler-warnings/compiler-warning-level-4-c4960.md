---
title: "Avertissement du compilateur (niveau&#160;4) C4960 | Microsoft Docs"
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
  - "C4960"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4960"
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4960
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' est trop grand pour être profilé  
  
 Quand vous avez utilisé [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un module d’entrée avec une fonction comprenant plus de 65 535 instructions. Une fonction de cette taille n’est pas disponible pour les optimisations guidées par profil.  
  
 Pour résoudre cet avertissement, réduisez la taille de la fonction.