---
title: "Erreur du compilateur C2911 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2911"
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2911
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : ne peut pas être déclaré ou défini dans la portée actuelle  
  
 Dans un espace de noms, une classe ou une fonction, vous ne pouvez définir qu’un membre du même espace de noms, de la même classe ou de la même fonction, ou encore un membre compris dans le même espace de noms, la même classe ou la même fonction.  
  
 L’exemple suivant génère l’erreur C2911 :  
  
```  
// C2911.cpp struct A; namespace M { struct D; } namespace N { struct C; namespace O { struct B; } // in N struct ::A {};   // C2911  A is member of global NS struct O::B{};   // OK B is in O, O is inside of N struct C {};     // OK C is member of N struct M::D {};  // C2911 D is member of M, M not enclosed by N }  
```