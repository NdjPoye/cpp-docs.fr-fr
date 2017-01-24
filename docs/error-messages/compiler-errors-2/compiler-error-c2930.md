---
title: "Erreur du compilateur C2930 | Microsoft Docs"
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
  - "C2930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2930"
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : type\-class\-id redéfini comme énumérateur de 'enum identifier'  
  
 Vous ne pouvez pas utiliser une classe générique ni de modèle en tant que membre d’une énumération.  
  
 Cette erreur peut être provoquée par une mise en correspondance incorrecte des accolades.  
  
 L’exemple suivant génère l’erreur C2930 :  
  
```  
// C2930.cpp // compile with: /c template<class T> class x{}; enum SomeEnum { x };   // C2930 class y{}; enum SomeEnum { y };  
```  
  
 L’erreur C2930 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2930c.cpp // compile with: /clr /c generic<class T> ref struct GC {}; enum SomeEnum { GC };   // C2930 ref struct GC2 {}; enum SomeEnum2 { GC2 };  
```