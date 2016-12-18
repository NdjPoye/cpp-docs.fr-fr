---
title: "Erreur du compilateur C2979 | Microsoft Docs"
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
  - "C2979"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2979"
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2979
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les spécialisations explicites ne sont pas prises en charge dans les génériques  
  
 Une classe générique a été déclarée incorrectement.  Pour plus d'informations, voir [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C2979.  
  
```  
// C2979.cpp // compile with: /clr /c generic <> ref class Utils {};   // C2979 error generic <class T> ref class Utils2 {};   // OK  
```