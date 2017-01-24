---
title: "Erreur du compilateur C2944 | Microsoft Docs"
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
  - "C2944"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2944"
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2944
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : type\-class\-id redéfini comme argument de valeur d’un modèle  
  
 Vous ne pouvez pas utiliser une classe générique ou de modèle à la place d’un symbole comme argument de valeur de modèle.  
  
 L’exemple suivant génère l’erreur C2944 :  
  
```  
// C2944.cpp // compile with: /c template<class T> class TC { }; template <int TC<int> > struct X1 { };   // C2944 template <class T > struct X2 {};  
```  
  
 L’erreur C2944 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2944b.cpp // compile with: /clr /c generic<class T> ref class GC {}; template <int GC<int> > struct X2 { };   // C2944 template <class T> struct X3 {};   // OK  
```