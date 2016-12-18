---
title: "Erreur du compilateur C3320 | Microsoft Docs"
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
  - "C3320"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3320"
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3320
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : le type ne peut pas avoir le même nom que la propriété 'name' du module  
  
 Un type défini par l’utilisateur \(UDT\) exporté, qui peut être struct, class, enum, union ou [\_\_value](../../misc/value.md), ne peut pas avoir le même nom que le paramètre passé à la propriété name de l’attribut [module](../../windows/module-cpp.md).  
  
 L’exemple suivant génère l’erreur C3320 :  
  
```  
// C3320.cpp #include "unknwn.h" [module(name="xx")]; [export] struct xx {   // C3320 // Try the following line instead // [export] struct yy { int i; };  
```