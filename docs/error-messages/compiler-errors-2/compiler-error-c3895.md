---
title: "Erreur du compilateur C3895 | Microsoft Docs"
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
  - "C3895"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3895"
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3895
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : les données membre type ne peuvent pas être 'volatile'  
  
 Certains types de données membre, par exemple [literal](../../windows/literal-cpp-component-extensions.md) ou [initonly](../../dotnet/initonly-cpp-cli.md), ne peuvent pas être [volatile](../../cpp/volatile-cpp.md).  
  
 L'exemple suivant génère l'erreur C3895 :  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```