---
title: "Avertissement du compilateur (niveau&#160;1) C4910 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4910"
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identificateur\>' : '\_\_declspec\(dllexport\)' et 'extern' sont incompatibles sur une instanciation explicite  
  
 L’instanciation de modèle explicite nommée *\<identificateur\>* est modifiée par les deux mots clés `__declspec(dllexport)` et `extern`. Toutefois, ces mots clés s’excluent mutuellement. Le mot clé `__declspec(dllexport)` signifie que la classe de modèle doit être instanciée, tandis que le mot clé `extern` signifie que la classe de modèle ne doit pas être instanciée automatiquement.  
  
## Voir aussi  
 [Instanciation explicite](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Règles générales et limitations](../../cpp/general-rules-and-limitations.md)