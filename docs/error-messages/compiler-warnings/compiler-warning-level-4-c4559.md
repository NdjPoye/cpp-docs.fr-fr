---
title: "Avertissement du compilateur (niveau 4) C4559 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4559"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4559"
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 4) C4559
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : redéfinition ; la fonction gagne \_\_declspec\(modifier\)  
  
 Une fonction a été redéfinie ou redéclarée et la deuxième définition ou déclaration possède un modificateur \_\_**declspec** \(***modifier*** supplémentaire.  Cet avertissement est informatif.  Pour résoudre cet avertissement, supprimez l'une des définitions.  
  
 L'exemple suivant génère l'erreur C4559 :  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```