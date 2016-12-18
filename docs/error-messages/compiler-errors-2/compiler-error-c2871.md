---
title: "Erreur du compilateur C2871 | Microsoft Docs"
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
  - "C2871"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2871"
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2871
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : un espace de noms avec ce nom n'existe pas  
  
 Cette erreur se produit lorsque vous passez à une directive [using](../Topic/using%20Directive%20\(C%23%20Reference\).md) un identificateur qui n'est pas un espace de noms.  
  
 L'exemple suivant génère l'erreur C2871 :  
  
```  
// C2871.cpp  
// compile with: /c  
using namespace d;   // C2871 d is not a namespace  
using namespace System;   // OK  
```