---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1100 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1100"
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable NMAKE U1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

macro 'nommacro' non conforme dans le contexte de la règle batch 'règle'  
  
 NMAKE génère cette erreur lorsque le bloc de commande d'une règle en mode batch fait directement ou indirectement référence à une macro de fichier spéciale qui n'est pas $\<.  
  
 $\< est la seule macro autorisée pour les règles en mode batch.