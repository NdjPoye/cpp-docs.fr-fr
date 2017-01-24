---
title: "Erreur du compilateur C3366 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3366"
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : les données membres static des types managés ou WinRT doivent être définies dans la définition de la classe  
  
 Vous avez tenté de référencer un membre statique d'une interface ou d'une classe WinRT ou .NET à l'extérieur de la définition de cette classe ou interface.  
  
 Le compilateur doit connaître la définition complète de la classe \(pour émettre les métadonnées après une passe\) et exige l'initialisation des membres de données statiques dans la classe.  
  
 Par exemple, l'exemple suivant génère l'erreur C3366 et montre comment la corriger :  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
  
 L'exemple suivant génère l'erreur C3366 et montre comment la corriger :  
  
```  
// C3366_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc struct X {  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```