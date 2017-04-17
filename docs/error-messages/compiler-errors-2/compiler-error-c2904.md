---
title: "Erreur du compilateur C2904 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2904"
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : nom déjà utilisé pour un modèle dans la portée actuelle  
  
 Vérifiez si le code contient des noms dupliqués.  
  
 L’exemple suivant génère l’erreur C2904 :  
  
```  
// C2904.cpp // compile with: /c void X();  // X is declared as a function template<class T> class X{};  // C2904  
```