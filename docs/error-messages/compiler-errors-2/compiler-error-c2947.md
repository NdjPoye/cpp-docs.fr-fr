---
title: "Erreur du compilateur C2947 | Microsoft Docs"
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
  - "C2947"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2947"
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2947
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\>' attendu pour terminer la construction, 'syntaxe' trouvé  
  
 Une liste d'arguments génériques ou template n'a pas pu être achevée correctement.  
  
 L'erreur C2947 peut également être générée par des erreurs de syntaxe.  
  
 L'exemple suivant génère l'erreur C2947 :  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```