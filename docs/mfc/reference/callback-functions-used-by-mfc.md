---
title: "Fonctions de rappel utilis&#233;es par MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions de rappel"
  - "fonctions de rappel, MFC"
  - "fonctions (C++), rappel"
  - "MFC, fonctions de rappel"
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions de rappel utilis&#233;es par MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Trois fonctions de rappel apparaissent dans la bibliothèque MFC.  Une description des fonctionnalités de rappel transmises à [CDC::EnumObjects](../Topic/CDC::EnumObjects.md), [CDC::GrayString](../Topic/CDC::GrayString.md), et [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) suit cette rubrique.  Pour l'utilisation générale des fonctions de rappel, consultez la section remarques de ces fonctions membres.  Notez que toutes les fonctions de rappel doivent intercepter les exceptions de MFC avant le renvoi à Windows, les exceptions ne peuvent pas être levées sur les limites de rappel.  Pour plus d'informations sur les exceptions, consultez l'article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)