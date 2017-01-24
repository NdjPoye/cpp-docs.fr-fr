---
title: "Avertissement du compilateur (niveau&#160;1) C4997 | Microsoft Docs"
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
  - "C4997"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4997"
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4997
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une coclasse n’implémente pas d’interface COM ou de pseudo\-interface  
  
 Une classe marquée avec l’attribut [coclasse](../../windows/coclass.md) n’implémente pas d’interface.  
  
 L’exemple suivant génère l’erreur C4997 :  
  
```  
// C4997.cpp // compile with: /WX // to resolve this C4997, uncomment all code #include <objbase.h> [ object ] __interface I { HRESULT func(); }; [ coclass ] struct C /*: I*/ { /* HRESULT func() { return S_OK; } */ };   // C4997  
```