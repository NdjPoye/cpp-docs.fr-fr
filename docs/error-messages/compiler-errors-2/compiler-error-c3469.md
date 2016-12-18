---
title: "Erreur du compilateur C3469 | Microsoft Docs"
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
  - "C3469"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3469"
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3469
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : impossible de transférer une classe générique  
  
 Vous ne pouvez pas utiliser le transfert de type sur une classe générique.  
  
 Pour plus d'informations, consultez [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant crée un composant.  
  
```  
// C3469.cpp // compile with: /clr /LD generic<typename T> public ref class GR {}; public ref class GR2 {};  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3466 :  
  
```  
// C3469_b.cpp // compile with: /clr /c #using "C3469.dll" [assembly:TypeForwardedTo(GR::typeid)];   // C3469 [assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```