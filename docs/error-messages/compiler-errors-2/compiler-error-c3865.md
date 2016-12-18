---
title: "Erreur du compilateur C3865 | Microsoft Docs"
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
  - "C3865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3865"
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'convention\_appel' : ne peut être utilisé que sur des fonctions membres natives  
  
 Une convention d'appel a été utilisée sur une fonction globale ou sur une fonction membre managée.  La convention d'appel ne peut être utilisée que sur une fonction membre native \(non managée\).  
  
 Pour plus d'informations, consultez [Conventions d'appel](../../cpp/calling-conventions.md).  
  
 L'exemple suivant génère l'erreur C3865 :  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```