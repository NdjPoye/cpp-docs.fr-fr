---
title: "Avertissement du compilateur (niveau&#160;1) C4794 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4794"
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Avertissement du compilateur (niveau&#160;1) C4794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

segment de variable de thread de stockage local 'variable' modifié de 'section name' en '.tls$'  
  
 Vous avez utilisé [\#pragma data\_seg](../../preprocessor/data-seg.md) pour placer une variable tls dans une section qui ne commence pas par .tls$.  
  
 La section .tls$*x* existe dans le fichier objet dans lequel sont définies des variables [\_\_declspec\(thread\)](../../cpp/thread.md). Une section .tls dans le fichier EXE ou DLL résulte de ces sections.  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4794 :  
  
```  
// C4794.cpp // compile with: /W1 /c #pragma data_seg(".someseg") __declspec(thread) int i;   // C4794 // OK #pragma data_seg(".tls$9") __declspec(thread) int j;  
```