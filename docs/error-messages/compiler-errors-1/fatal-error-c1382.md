---
title: "Erreur irr&#233;cup&#233;rable C1382 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1382"
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier PCH 'fichier' recompilé depuis la génération de 'obj'.Régénérez cet objet  
  
 Lors de l'utilisation de [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un fichier .pch qui était plus récent qu'un fichier CIL .obj qui pointe vers lui.  Les informations dans le fichier CIL .obj sont périmées.  Régénérez l'objet.  
  
 L'erreur C1382 peut également se produire si vous compilez avec **\/Yc**, mais aussi si vous passez plusieurs fichiers de code source au compilateur.  Pour y remédier, n'utilisez pas **\/Yc** lors du passage de plusieurs fichiers de code source au compilateur.  Pour plus d'informations, consultez [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md).