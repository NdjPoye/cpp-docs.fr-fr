---
title: "Erreur du compilateur C2507 | Microsoft Docs"
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
  - "C2507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2507"
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : modificateurs virtuels sur la classe de base trop nombreux  
  
 Une classe ou une structure est déclarée plusieurs fois comme étant `virtual`.  Un seul modificateur `virtual` peut apparaître pour chaque classe dans une liste de classes de base.  
  
 L'exemple suivant génère l'erreur C2507 :  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```