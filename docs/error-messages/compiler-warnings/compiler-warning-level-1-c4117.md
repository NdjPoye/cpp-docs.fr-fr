---
title: "Avertissement du compilateur (niveau&#160;1) C4117 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4117"
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nom de macro 'name' réservé, 'Command' ignoré  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Tentative de définition ou de suppression de la définition d’une macro prédéfinie.  
  
2.  Tentative de définition ou de suppression de la définition de l’opérateur de préprocesseur **defined**.  
  
 L’exemple suivant génère l’avertissement C4117 :  
  
```  
// C4117.cpp // compile with: /W1 #define __FILE__ test         // C4117. __FILE__ is a predefined macro #define ValidMacroName test   // ok int main() { }  
```