---
title: "Erreur du compilateur C2006 | Microsoft Docs"
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
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'directive' : nom de fichier attendu, 'jeton' rencontré  
  
 Les directives telles que [\#include](../../preprocessor/hash-include-directive-c-cpp.md) ou [\#import](../../preprocessor/hash-import-directive-cpp.md) requièrent un nom de fichier.  Pour corriger l'erreur, vérifiez que *jeton* est un nom de fichier valide.  Placez aussi le nom de fichier entre guillemets doubles ou entre signes inférieur à et supérieur à.  
  
 L'exemple suivant génère l'erreur C2006 :  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Résolution possible :  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```