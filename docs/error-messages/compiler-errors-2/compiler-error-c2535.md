---
title: "Erreur du compilateur C2535 | Microsoft Docs"
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
  - "C2535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2535"
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : fonction membre déjà définie ou déclarée  
  
 Cette erreur peut être provoquée par l'utilisation de la même liste de paramètres formels dans plusieurs définitions ou déclarations d'une fonction surchargée.  
  
 Si l'erreur C2535 est générée en raison de la fonction Dispose, consultez [Destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) pour plus d'informations.  
  
 Si vous compilez un projet ATL, consultez l'article Q241852 de la Base de connaissances.  
  
 L'exemple suivant génère l'erreur C2535 :  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```