---
title: "Erreur du compilateur C3858 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3858"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3858"
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3858
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ne peut pas être redéclaré dans la portée actuelle  
  
 Le type ne peut pas être déclaré deux fois dans la même portée.  
  
 L'exemple suivant génère l'erreur C3858 :  
  
```  
// C3858.cpp  
// compile with: /LD  
template <class T>  
struct Outer  
{  
   struct Inner;  
};  
  
template <class T>  
struct Outer<T>::Inner;   // C3858  
// try the following line instead  
// struct Outer<T>::Inner{};  
```