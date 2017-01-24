---
title: "Erreur du compilateur C2798 | Microsoft Docs"
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
  - "C2798"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2798"
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2798
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super::membre' est ambigu  
  
 Plusieurs structures héritées contiennent le membre que vous avez référencé à l'aide de [super](../../cpp/super.md).  Pour corriger cette erreur, vous pouvez au choix :  
  
-   supprimer B1 ou B2 de la liste d'héritage de D ;  
  
-   modifier le nom des données membres dans B1 ou B2.  
  
 L'exemple suivant génère l'erreur C2798 :  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```