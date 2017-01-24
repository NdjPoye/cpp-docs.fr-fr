---
title: "Erreur du compilateur C3232 | Microsoft Docs"
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
  - "C3232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3232"
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : impossible d’utiliser un paramètre de type générique dans un nom qualifié  
  
 Un paramètre de type générique a été utilisé de façon incorrecte.  
  
 L’exemple suivant génère l’erreur C3232 :  
  
```  
// C3232.cpp // compile with: /clr generic <class T> ref class C { typename T::TYPE t;   // C3232 };  
```