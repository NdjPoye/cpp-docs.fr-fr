---
title: "Avertissement du compilateur (niveau&#160;4) C4932 | Microsoft Docs"
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
  - "C4932"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4932"
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4932
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_identifier\(identifier\) et \_\_identifier\(identifier\) sont impossibles à distinguer  
  
 Le compilateur ne peut pas faire la distinction entre **\_finally** et `__finally` ou `__try` et **\_try** en tant que paramètre passé à [\_\_identifier](../../windows/identifier-cpp-cli.md). Vous ne devez pas essayer de les utiliser tous les deux en tant qu’identificateurs dans le même programme, car cela se traduit par une erreur [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md).  
  
 L’exemple suivant génère l’erreur C4932 :  
  
```  
// C4932.cpp // compile with: /clr /W4 /WX int main() { int __identifier(_finally) = 245;   // C4932 int __identifier(__finally) = 25;   // C4932 }  
```