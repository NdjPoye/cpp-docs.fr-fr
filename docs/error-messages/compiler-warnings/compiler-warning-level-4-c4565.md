---
title: "Avertissement du compilateur (niveau 4) C4565 | Microsoft Docs"
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
  - "C4565"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4565"
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4565
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : redéfinition ; le symbole était déclaré précédemment avec \_\_declspec\(\)  
  
 Un symbole a été redéfini ou redéclaré et la deuxième définition ou déclaration, contrairement à la première, ne comprenait pas de modificateur `__declspec` \(***modifier***.  Cet avertissement est informatif.  Pour résoudre cet avertissement, supprimez l'une des définitions.  
  
 L'exemple suivant génère l'erreur C4565 :  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```