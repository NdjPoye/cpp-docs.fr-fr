---
title: "Erreur du compilateur C2939 | Microsoft Docs"
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
  - "C2939"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2939"
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2939
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : type\-class\-id redéfini comme variable locale de données  
  
 Vous ne pouvez pas utiliser une classe générique ou de modèle comme variable locale de données.  
  
 Cette erreur peut se produire si des accolades sont appariées incorrectement.  
  
 L’exemple suivant génère l’erreur C2939 :  
  
```  
// C2939.cpp template<class T> struct TC { }; int main() { int TC<int>;   // C2939 int TC;   // OK }  
```  
  
 L’erreur C2939 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2939b.cpp // compile with: /clr generic<class T> ref struct GC { }; int main() { int GC<int>;   // C2939 int GC;   // OK }  
```