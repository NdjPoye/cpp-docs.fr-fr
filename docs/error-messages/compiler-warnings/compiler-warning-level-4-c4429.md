---
title: "Avertissement du compilateur (niveau 4) C4429 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4429"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4429"
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 4) C4429
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nom de caractère universel éventuellement incomplet ou incorrectement formé  
  
 Le compilateur a détecté une séquence de caractères qui peut être un nom de caractère universel de format incorrect.  Un nom de caractère universel est composé de `\u` suivi de quatre chiffres hexadécimaux, ou `\U` suivi de huit chiffres hexadécimaux.  
  
 L'exemple suivant génère l'erreur C4429 :  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```