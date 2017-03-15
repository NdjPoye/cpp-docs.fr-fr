---
title: "Erreur irr&#233;cup&#233;rable C1852 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1852"
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable C1852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom\_fichier' n’est pas un fichier d’en\-tête précompilé valide  
  
 Le fichier n’est pas un en\-tête précompilé.  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Fichier non valide spécifié avec **\/Yu** ou **\#pragma hdrstop**.  
  
2.  Le compilateur suppose que l’extension de fichier est .pch, sauf indication contraire de votre part.