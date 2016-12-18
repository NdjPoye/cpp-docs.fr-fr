---
title: "Avertissement du compilateur (niveau&#160;1) C4805 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4805"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4805"
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4805
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : mélange risqué de type 'type' et type 'type' dans l’opération  
  
 Cet avertissement est généré pour les opérations de comparaison entre [bool](../../cpp/bool-cpp.md) et [int](../../c-language/integer-types.md). L’exemple suivant génère l’erreur C4805 :  
  
```  
// C4805.cpp // compile with: /W1 int main() { int i = 1; bool b = true; if (i == b) {   // C4805, comparing bool and int variables } }  
```