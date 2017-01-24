---
title: "Erreur du compilateur C3354 | Microsoft Docs"
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
  - "C3354"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3354"
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3354
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la fonction utilisée pour créer un délégué ne peut pas avoir un type de retour 'type'  
  
 Les types suivants ne sont pas des types de retour valides pour un [délégué](../../misc/delegate.md) :  
  
-   Pointeur vers fonction  
  
-   Pointeur vers membre  
  
-   Pointeur vers fonction membre  
  
-   Référence vers fonction  
  
-   Référence vers fonction membre  
  
 L’exemple suivant génère l’erreur C3354 :  
  
```  
// C3354_2.cpp // compile with: /clr /c using namespace System; typedef void ( *VoidPfn )(); delegate VoidPfn func(); // C3354 // try the following line instead // delegate  void func();  
```  
  
 L’exemple suivant génère l’erreur C3354 :  
  
```  
// C3354.cpp // compile with: /clr:oldSyntax /c #using <mscorlib.dll> using namespace System; typedef void (*VoidPfn)(); __delegate VoidPfn func();   // C3354 // try the following line instead // __delegate void func();  
```