---
title: "Erreur du compilateur C3880 | Microsoft Docs"
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
  - "C3880"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3880"
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3880
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : ne peut pas représenter une donnée membre littérale  
  
 Le type d'un attribut [littéral](../../windows/literal-cpp-component-extensions.md) doit posséder un des types suivants ou pouvoir être converti dans un de ceux\-ci au moment de la compilation :  
  
-   type intégral  
  
-   string  
  
-   enum avec un type intégral ou sous\-jacent  
  
 L'exemple suivant génère l'erreur C3880 :  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```