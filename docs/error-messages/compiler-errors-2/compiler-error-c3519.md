---
title: "Erreur du compilateur C3519 | Microsoft Docs"
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
  - "C3519"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3519"
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3519
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param\_non\_valide' : paramètre non valide de l'attribut embedded\_idl  
  
 Un paramètre a été passé à l'attribut `embedded_idl` de [\#import](../../preprocessor/hash-import-directive-cpp.md), mais le compilateur ne l'a pas reconnu.  
  
 Les seuls paramètres autorisés pour `embedded_idl` sont `emitidl` et `no_emitidl`.  
  
 L'exemple suivant génère l'erreur C3519 :  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```