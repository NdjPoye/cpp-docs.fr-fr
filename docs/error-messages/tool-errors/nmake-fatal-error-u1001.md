---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1001 | Microsoft Docs"
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
  - "U1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1001"
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de syntaxe : caractère non conforme 'caractère' dans la macro  
  
 Le caractère donné apparaît dans une macro, mais ne correspond ni à une lettre, ni à un nombre ni à un trait de soulignement.  
  
 Cette erreur peut être provoquée par un signe des deux\-points manquant dans une expansion macro :  
  
```  
syntax error : illegal character '=' in macro  
```