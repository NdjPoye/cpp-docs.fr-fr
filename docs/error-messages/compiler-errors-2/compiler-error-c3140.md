---
title: "Erreur du compilateur C3140 | Microsoft Docs"
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
  - "C3140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3140"
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'avoir plusieurs attributs 'module' dans la même unité de compilation  
  
 L'attribut [module](../../windows/module-cpp.md) ne peut être défini qu'une seule fois par projet.  
  
 L'exemple suivant génère l'erreur C3140 :  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```