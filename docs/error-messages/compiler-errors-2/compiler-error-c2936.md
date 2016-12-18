---
title: "Erreur du compilateur C2936 | Microsoft Docs"
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
  - "C2936"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2936"
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2936
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : type\-class\-id redéfini comme variable globale de données  
  
 Vous ne pouvez pas utiliser une classe générique ni de modèle comme variable globale de données.  
  
 Cette erreur peut être provoquée par une mise en correspondance incorrecte des accolades.  
  
 L’exemple suivant génère l’erreur C2936 :  
  
```  
// C2936.cpp // compile with: /c template<class T> struct TC { }; int TC<int>;   // C2936 // OK struct TC2 { }; int TC2;  
```  
  
 L’erreur C2936 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2936b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; int GC<int>;   // C2936 // OK ref struct GC2 {}; int GC2;  
```