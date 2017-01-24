---
title: "Erreur du compilateur C2838 | Microsoft Docs"
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
  - "C2838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2838"
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : nom qualifié non conforme dans une déclaration de membre  
  
 Une classe, structure ou union emploie un nom qualifié complet pour redéclarer un membre d'une autre classe, structure ou union.  
  
 L'exemple suivant génère l'erreur C2838 :  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```