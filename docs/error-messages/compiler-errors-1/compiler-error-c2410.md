---
title: "Erreur du compilateur C2410 | Microsoft Docs"
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
  - "C2410"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2410"
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2410
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : nom de membre ambigu dans le 'contexte'  
  
 L'identificateur est un membre de plusieurs structures ou unions dans ce contexte.  
  
 Utilisez un spécificateur d'union ou de structure sur l'opérande qui a provoqué l'erreur.  Un spécificateur d'union ou de structure est un identificateur de type `struct` ou une `union` \(nom `typedef` ou variable de même type que la structure ou l'union référencée\).  Le spécificateur doit être l'opérande gauche du premier opérateur de sélection des membres \(.\) qui va utiliser l'opérande.