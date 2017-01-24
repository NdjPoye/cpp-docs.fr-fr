---
title: "Avertissement du compilateur (niveau 1) C4618 | Microsoft Docs"
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
  - "C4618"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4618"
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4618
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les paramètres pragma comportaient une chaîne vide ; pragma ignoré  
  
 Une chaîne nulle a été attribuée comme argument d'un **\#pragma**.  
  
 Le pragma a été traité sans l'argument.  
  
 L'exemple suivant génère l'erreur C4618 :  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```