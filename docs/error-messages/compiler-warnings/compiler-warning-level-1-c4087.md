---
title: "Avertissement du compilateur (niveau&#160;1) C4087 | Microsoft Docs"
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
  - "C4087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4087"
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : déclaré avec une liste de paramètres 'void'  
  
 La déclaration de fonction n’a aucun paramètre formel, mais l’appel de fonction a des paramètres réels. Des paramètres supplémentaires sont passés selon la convention d’appel de la fonction.  
  
 Cet avertissement concerne le compilateur C.  
  
## Exemple  
  
```  
// C4087.c // compile with: /W1 int f1( void ) { } int main() { f1( 10 );   // C4087 }  
```