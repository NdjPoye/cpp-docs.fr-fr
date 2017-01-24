---
title: "Avertissement du compilateur (niveau 4) C4207 | Microsoft Docs"
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
  - "C4207"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4207"
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4207
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : forme de l'initialiseur étendue  
  
 Avec les extensions Microsoft \(\/Ze\), vous pouvez initialiser un tableau de `char` non dimensionné avec une chaîne entre accolades.  
  
## Exemple  
  
```  
// C4207.c  
// compile with: /W4  
char c[] = { 'a', 'b', "cdefg" }; // C4207  
  
int main()  
{  
}  
```  
  
 De telles initialisations sont non valides sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).