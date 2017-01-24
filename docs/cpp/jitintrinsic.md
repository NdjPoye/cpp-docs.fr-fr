---
title: "jitintrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "jitintrinsic"
  - "jitintrinsic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), jitintrinsic"
  - "jitintrinsic __declspec (modificateur)"
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# jitintrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Marque la fonction comme significative pour le CLR \(Common Langage Runtime\) 64 bits.  Ceci est utilisé pour certaines fonctions dans les bibliothèques fournies par Microsoft.  
  
## Syntaxe  
  
```  
__declspec(jitintrinsic)  
```  
  
## Notes  
 `jitintrinsic` ajoute un MODOPT \(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>\) à la signature de la fonction.  
  
 Il est déconseillé aux utilisateurs d'avoir recours à ce modificateur `__declspec`, car des résultats inattendus peuvent survenir.  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)