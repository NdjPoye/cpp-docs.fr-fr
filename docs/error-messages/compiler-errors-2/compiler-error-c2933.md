---
title: "Erreur du compilateur C2933 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2933"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2933"
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2933
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : type\-class\-id redéfini en tant que membre typedef d’'identifier'  
  
 Vous ne pouvez pas utiliser une classe générique ou de modèle en tant que membre `typedef`.  
  
 L’exemple suivant génère l’erreur C2933 :  
  
```  
// C2933.cpp // compile with: /c template<class T> struct TC { }; struct MyStruct { typedef int TC<int>;   // C2933 }; struct TC2 { }; struct MyStruct2 { typedef int TC2; };  
```  
  
 L’erreur C2933 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2933b.cpp // compile with: /clr /c generic<class T> ref struct GC { }; struct MyStruct { typedef int GC<int>;   // C2933 }; ref struct GC2 { }; struct MyStruct2 { typedef int GC2; };  
```