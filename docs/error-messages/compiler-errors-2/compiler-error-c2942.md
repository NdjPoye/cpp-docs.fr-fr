---
title: "Erreur du compilateur C2942 | Microsoft Docs"
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
  - "C2942"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2942"
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2942
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : type\-class\-id redéfini comme argument formel d’une fonction  
  
 Vous ne pouvez pas utiliser une classe générique ou de modèle comme argument formel. Vous ne pouvez pas passer un argument directement au constructeur d’une classe générique ou de modèle.  
  
 L’exemple suivant génère l’erreur C2942 :  
  
```  
  
// C2942.cpp // compile with: /c template<class T> struct TC {}; void f(int TC<int>) {}   // C2942 // OK struct TC2 {}; void f(TC2 i) {}  
```  
  
 L’erreur C2942 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2942b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; void f(int GC<int>) {}   // C2942 ref struct GC2 { }; void f(int GC2) {}  
```