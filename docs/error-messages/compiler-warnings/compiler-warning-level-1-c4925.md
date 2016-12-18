---
title: "Avertissement du compilateur (niveau&#160;1) C4925 | Microsoft Docs"
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
  - "C4925"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4925"
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4925
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : la méthode dispinterface ne peut pas être appelée à partir d’un script  
  
 Les langages de script ne peuvent pas créer de paramètres VT\_BYREF « in », mais uniquement des paramètres VT\_BYREF « out ».  
  
 Pour résoudre cet avertissement, vous pouvez également ne pas faire du paramètre un type pointeur \(dans la définition et l’implémentation\).  
  
 L’exemple suivant génère l’avertissement C4925 :  
  
```  
// C4925.cpp // compile with: /LD /W1 #define _ATL_ATTRIBUTES 1 #include <atlbase.h> #include <atlcom.h> [ module(name="Test")]; [ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ] __interface IDisp { [id(9)] void f([in] int*); }; [ coclass, uuid("00000000-0000-0000-0000-000000000002")  ] struct CDisp : IDisp {   // C4925 void f(int*) {} };  
```