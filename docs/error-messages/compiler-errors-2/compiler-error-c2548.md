---
title: "Erreur du compilateur C2548 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2548"
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::membre' : paramètre par défaut manquant pour le paramètre 'paramètre'  
  
 Il manque un paramètre à la liste de paramètres par défaut.  Si vous indiquez un paramètre par défaut à un endroit quelconque d'une liste de paramètres, vous devez définir les paramètres par défaut de tous les paramètres suivants.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2548 :  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```