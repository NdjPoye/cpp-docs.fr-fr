---
title: "Erreur du compilateur C3198 | Microsoft Docs"
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
  - "C3198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3198"
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

utilisation non valide des pragmas à virgule flottante : le pragma fenv\_access ne fonctionne qu'en mode précision  
  
 Le pragma [fenv\_access](../../preprocessor/fenv-access.md) a été utilisé sous un paramètre [fp](../../build/reference/fp-specify-floating-point-behavior.md) autre que **\/fp:precise**.  
  
 L'exemple suivant génère l'erreur C3198 :  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```