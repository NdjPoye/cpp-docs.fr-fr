---
title: "Avertissement du compilateur (niveau 1) C4652 | Microsoft Docs"
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
  - "C4652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4652"
ms.assetid: 2cf2c666-8cdd-4dd9-bda0-662921498b03
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

option du compilateur 'option' non cohérente avec l'en\-tête précompilé ; l'option active de ligne de commande se substituera à celle qui était définie dans l'en\-tête précompilé  
  
 L'option donnée de la ligne de commande était différente de celle qui était donnée lors de la création de l'en\-tête précompilé \(.pch\).  C'est l'option spécifiée dans la ligne de commande active qui a été utilisée.  
  
 Vous pouvez éviter cet avertissement en régénérant le fichier d'en\-tête précompilé avec l'option de ligne de commande donnée.