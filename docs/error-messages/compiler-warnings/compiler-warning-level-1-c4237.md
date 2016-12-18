---
title: "Avertissement du compilateur (niveau 1) C4237 | Microsoft Docs"
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
  - "C4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4237"
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

mot clé 'MotClé' non pris en charge pour l'instant mais réservé pour un usage ultérieur  
  
 Un mot clé contenu dans la spécification C\+\+ n'est pas implémenté dans le compilateur Visual C\+\+, mais il n'est pas disponible comme symbole défini par l'utilisateur.  
  
 L'exemple suivant génère l'erreur C4237 :  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```