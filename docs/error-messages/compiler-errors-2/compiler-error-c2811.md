---
title: "Erreur du compilateur C2811 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2811"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2811"
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2811
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' : ne peut pas hériter de 'type2', une classe ref peut uniquement hériter d'une classe ref ou d'une classe interface  
  
 Vous avez essayé d'utiliser une classe non managée comme classe de base pour une classe managée.  
  
 L'exemple suivant génère l'erreur C2811 :  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```