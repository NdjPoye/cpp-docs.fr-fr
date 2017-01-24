---
title: "Erreur des outils &#201;diteur de liens LNK1264 | Microsoft Docs"
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
  - "LNK1264"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1264"
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1264
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/LTCG:PGINSTRUMENT spécifié mais aucune génération de code requise ; l'instrumentation a échoué  
  
 **\/LTCG:PGINSTRUMENT** a été spécifié, mais aucun fichier .obj compilé avec [\/GL](../../build/reference/gl-whole-program-optimization.md) n'a été trouvé.  L'instrumentation ne peut pas s'effectuer, l'édition de liens a échoué.  Il doit y avoir au moins un fichier .obj sur la ligne de commande compilée avec **\/GL** pour permettre l'instrumentation.  
  
 PGO \(Profile Guided Optimization\) est disponible uniquement dans les compilateurs 64 bits.