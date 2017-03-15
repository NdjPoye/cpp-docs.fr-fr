---
title: "Erreur du compilateur C2755 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2755"
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : un paramètre sans type d'une spécialisation partielle doit être un identificateur simple  
  
 Le paramètre sans type doit être un identificateur simple, élément que le compilateur peut résoudre au moment de la compilation en un identificateur simple ou une valeur de constante.  
  
 L'exemple suivant génère l'erreur C2755 :  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```