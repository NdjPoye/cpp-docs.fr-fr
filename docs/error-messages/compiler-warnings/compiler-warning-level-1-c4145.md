---
title: "Avertissement du compilateur (niveau&#160;1)&#160;C4145 | Microsoft Docs"
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
  - "C4145"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4145"
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1)&#160;C4145
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression1' : expression relationnelle comme expression de switch ; risque de confusion avec 'expression2'  
  
 Une instruction `switch` utilise une expression relationnelle comme son expression de contrôle, ce qui produit une valeur booléenne pour les instructions **case**. Voulez\-vous utiliser *expression2* ?  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4145 :  
  
```  
// C4145.cpp // compile with: /W1 int main() { int i = 0; switch(i == 1) {   // C4145, use i instead of i == 1 to resolve case 1: break; default: break; } }  
```