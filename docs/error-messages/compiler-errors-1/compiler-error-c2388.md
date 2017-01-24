---
title: "Erreur du compilateur C2388 | Microsoft Docs"
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
  - "C2388"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2388"
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2388
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : un symbole ne peut pas être déclaré avec \_\_declspec\(appdomain\) et \_\_declspec\(process\)  
  
 Vous ne pouvez pas utiliser les modificateurs `__declspec``appdomain` et `process` sur le même symbole.  Le stockage d’une variable existe par processus ou par domaine d’application.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [process](../../cpp/process.md).  
  
 L’exemple suivant génère l’erreur C2388 :  
  
```  
// C2388.cpp // compile with: /clr /c __declspec(process) __declspec(appdomain) int i;   // C2388 __declspec(appdomain) int i;   // OK  
```