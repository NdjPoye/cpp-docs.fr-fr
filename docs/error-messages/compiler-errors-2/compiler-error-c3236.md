---
title: "Erreur du compilateur C3236 | Microsoft Docs"
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
  - "C3236"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3236"
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3236
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'instanciation explicite d'un générique n'est pas autorisée  
  
 Le compilateur n’autorise pas l’instanciation explicite de classes génériques.  
  
 L’exemple suivant génère l’erreur C3236 :  
  
```  
// C3236.cpp // compile with: /clr generic<class T> public ref class X {}; generic ref class X<int>;   // C3236  
```  
  
 L’exemple suivant illustre une résolution possible :  
  
```  
// C3236b.cpp // compile with: /clr /c generic<class T> public ref class X {};  
```