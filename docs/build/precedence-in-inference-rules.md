---
title: "Priorit&#233; dans les r&#232;gles d&#39;inf&#233;rence | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "règles d'inférence dans NMAKE"
  - "priorité, règle d'inférence"
  - "règles, inférence"
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Priorit&#233; dans les r&#232;gles d&#39;inf&#233;rence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une règle d'inférence possède plusieurs définitions, NMAKE utilise celle qui a la plus haute priorité.  Le tableau ci\-dessous présente les règles d'inférence par ordre de priorité décroissante :  
  
1.  Règle d'inférence définie dans un makefile ; les définitions les plus récentes sont prioritaires.  
  
2.  Règle d'inférence définie dans Tools.ini ; les définitions les plus récentes sont prioritaires.  
  
3.  Règle d'inférence prédéfinie.  
  
## Voir aussi  
 [Règles d'inférence](../build/inference-rules.md)