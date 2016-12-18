---
title: "Erreur des outils &#201;diteur de liens LNK1166 | Microsoft Docs"
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
  - "LNK1166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1166"
ms.assetid: d69548a8-0efb-44e1-90b7-b27636a4b575
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ne peut pas ajuster le code à offset\=offset, va\=value  
  
 LINK n'a pas pu effectuer le remplissage de code nécessaire.  
  
 Certaines instructions ne doivent pas s'étendre sur des frontières de pages pour certains processeurs.  LINK tente d'ajouter des remplissages pour corriger cette situation.  Dans ce cas, LINK n'a pas pu éviter le problème.