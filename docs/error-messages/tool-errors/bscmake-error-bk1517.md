---
title: "Erreur BSCMAKE BK1517 | Microsoft Docs"
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
  - "BK1517"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1517"
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur BSCMAKE BK1517
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier source de fichiersbr compilé avec \/Yc et \/Yu  
  
 Le fichier .sbr fait référence à lui\-même.  Il a probablement été recompilé avec \/Yu après avoir été compilé avec \/Yc.  Réinitialisez l'option de compilateur \/Yc pour le fichier source, puis sélectionnez **Régénérer** pour générer de nouveaux fichiers .sbr.  Ne recompilez pas le fichier source avec l'option \/Yu.