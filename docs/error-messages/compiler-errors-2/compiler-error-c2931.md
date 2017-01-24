---
title: "Erreur du compilateur C2931 | Microsoft Docs"
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
  - "C2931"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2931"
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2931
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : type\-class\-id redéfini en tant que fonction membre d’'identifier'  
  
 Vous ne pouvez pas utiliser une classe ou un modèle générique en tant que fonction membre d’une autre classe.  
  
 Cette erreur peut être provoquée si des accolades sont incorrectement appariées.  
  
 L’exemple suivant génère l’erreur C2931 :  
  
```  
// C2931.cpp // compile with: /c template<class T> struct TC { }; struct MyStruct { void TC<int>();   // C2931 }; struct TC2 { }; struct MyStruct2 { void TC2(); };  
```  
  
 L’erreur C2931 peut également se produire lors de l’utilisation de génériques.  
  
```  
// C2931b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; struct MyStruct { void GC<int>();   // C2931 void GC2();   // OK };  
```