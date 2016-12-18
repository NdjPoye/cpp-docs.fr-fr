---
title: "Utilisation de abort | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort (fonction)"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de abort
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'appel de la fonction [abort](../c-runtime-library/reference/abort.md) provoque l'arrêt immédiat.  Il ignore le processus normal de destruction des objets statiques globaux initialisés.  Il ignore également tout traitement spécial qui a été spécifié avec la fonction `atexit`.  
  
## Voir aussi  
 [Considérations supplémentaires sur la terminaison](../cpp/additional-termination-considerations.md)