---
title: "Erreur du compilateur C3467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3467"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3467"
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3467
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ce type a déjà été transféré  
  
 Le compilateur a détecté plusieurs déclarations de type de transfert pour un même type. Seule une déclaration est autorisée par type.  
  
 Pour plus d'informations, consultez [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant crée un composant.  
  
```  
// C3467.cpp // compile with: /LD /clr public ref class R {};  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3467 :  
  
```  
// C3467_b.cpp // compile with: /clr /c #using "C3467.dll" [ assembly:TypeForwardedTo(R::typeid) ]; [ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```