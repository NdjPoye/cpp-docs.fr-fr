---
title: "Erreur du compilateur C2572 | Microsoft Docs"
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
  - "C2572"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2572"
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2572
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::membre' : redéfinition du paramètre par défaut : paramètre param  
  
 Il n'est pas possible de redéfinir les paramètres par défaut.  Si vous avez besoin d'une autre valeur pour le paramètre, le paramètre par défaut doit rester indéfini.  
  
 L'exemple suivant génère l'erreur C2572 :  
  
```  
// C2572.cpp  
// compile with: /c  
void f(int i = 1);   // function declaration  
  
// function definition  
void f(int i = 1) {}   // C2572  
  
// try the following line instead  
// void f(int i) {}  
```