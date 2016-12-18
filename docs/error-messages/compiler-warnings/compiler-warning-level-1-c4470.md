---
title: "Avertissement du compilateur (niveau 1) C4470 | Microsoft Docs"
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
  - "C4470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4470"
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragmas de contrôle à virgule flottante ignorés sous \/clr  
  
 Les pragmas de contrôle à virgule flottante :  
  
-   [fenv\_access](../../preprocessor/fenv-access.md)  
  
-   [float\_control](../../preprocessor/float-control.md)  
  
-   [fp\_contract](../../preprocessor/fp-contract.md)  
  
 n'ont aucun effet sous [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L'exemple suivant génère l'erreur C4470 :  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```