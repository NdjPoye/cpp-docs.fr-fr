---
title: "Erreur du compilateur C3283 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3283"
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une interface ne peut pas avoir de constructeur d’instance  
  
 Une [interface](../../windows/interface-class-cpp-component-extensions.md) CLR ne peut pas avoir de constructeur d’instance.  Un constructeur statique est autorisé.  
  
 L’exemple suivant génère l’erreur C3283 :  
  
```  
// C3283.cpp // compile with: /clr interface class I { I();   // C3283 };  
```  
  
 Résolution possible :  
  
```  
// C3283b.cpp // compile with: /clr /c interface class I { static I(){} };  
```