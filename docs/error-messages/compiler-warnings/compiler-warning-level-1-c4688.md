---
title: "Avertissement du compilateur (niveau&#160;1) C4688 | Microsoft Docs"
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
  - "C4688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4688"
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constraint' : la liste des contraintes contient un type privé d’assembly 'type'  
  
 Une liste de contraintes possède un type privé d’assembly, ce qui signifie qu’il ne sera pas accessible en dehors de l’assembly. Pour plus d’informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4688.  
  
```  
// C4688.cpp // compile with: /clr /c /W1 ref struct A {};   // private type public ref struct B {}; // Delete the following 3 lines to resolve. generic <class T> where T : A   // C4688 public ref struct M {}; generic <class T> where T : B public ref struct N {};  
```