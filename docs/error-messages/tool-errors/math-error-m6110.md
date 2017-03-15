---
title: "Erreur math&#233;matique M6110 | Microsoft Docs"
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
  - "M6110"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6110"
ms.assetid: aac9ae37-6a6d-46e9-85d4-dfe03f1c3e11
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur math&#233;matique M6110
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dépassement de capacité de la pile  
  
 Une expression à virgule flottante a provoqué un dépassement de capacité de la pile à virgule flottante.  
  
 Les exceptions de virgule flottante de dépassement de la capacité de la pile sont interceptées jusqu'à une limite de sept niveaux en plus des huit niveaux généralement pris en charge par le coprocesseur 8087\/287\/387.  
  
 Le programme se termine par le code de sortie 138.