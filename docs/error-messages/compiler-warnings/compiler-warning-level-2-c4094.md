---
title: "Avertissement du compilateur (niveau 2) C4094 | Microsoft Docs"
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
  - "C4094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4094"
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'jeton' sans balise n'a déclaré aucun symbole  
  
 Le compilateur a détecté une déclaration vide utilisant une structure, une union ou une classe sans balise.  La déclaration est ignorée.  
  
## Exemple  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 Cette condition génère une erreur sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).