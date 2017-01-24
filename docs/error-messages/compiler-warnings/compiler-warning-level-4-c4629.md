---
title: "Avertissement du compilateur (niveau&#160;4) C4629 | Microsoft Docs"
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
  - "C4629"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4629"
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4629
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

digrammes utilisés, séquence de caractères 'digramme' interprétée comme jeton 'caractère' \(insérez un espace entre les deux caractères si cela n’est pas ce que vous souhaitiez\)  
  
 Sous [\/Za](../../build/reference/za-ze-disable-language-extensions.md), le compilateur vous avertit quand il détecte un digramme.  
  
 L’exemple suivant génère l’avertissement C4629 :  
  
```  
// C4629.cpp // compile with: /Za /W4 int main() <%   // C4629 <% digraph for { }  
```