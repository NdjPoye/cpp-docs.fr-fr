---
title: "Erreur du compilateur C2032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2032"
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : la fonction ne peut pas être membre de struct\/union 'StructOuUnion'  
  
 La structure ou l'union a une fonction membre, ce qui est autorisé en C\+\+, mais pas en C.  Pour corriger l'erreur, compilez le code sous la forme d'un programme C\+\+ ou supprimez la fonction membre.  
  
 L'exemple suivant génère l'erreur C2032 :  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Résolution possible :  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```