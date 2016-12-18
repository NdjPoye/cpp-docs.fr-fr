---
title: "Erreur du compilateur C2632 | Microsoft Docs"
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
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' ne peut pas être suivi de 'type2'  
  
 Cette erreur peut être provoquée s'il manque du code entre deux spécificateurs de type.  
  
 L'exemple suivant génère l'erreur C2632 :  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003.  `bool` est désormais un type approprié.  Dans les versions précédentes, `bool` était un typedef et vous pouviez créer des identificateurs sous ce nom.  
  
 L'exemple suivant génère l'erreur C2632 :  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Pour corriger cette erreur de façon que le code soit valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+, renommez l'identificateur.