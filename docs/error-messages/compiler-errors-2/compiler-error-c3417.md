---
title: "Erreur du compilateur C3417 | Microsoft Docs"
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
  - "C3417"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3417"
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3417
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : les types valeur ne peuvent pas contenir de fonctions membres spéciales définies par l'utilisateur  
  
 Les types valeur ne peuvent pas contenir de fonctions telles qu'un constructeur d'instance par défaut, un destructeur ou un constructeur de copie.  
  
 L'exemple suivant génère l'erreur C3517 :  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```