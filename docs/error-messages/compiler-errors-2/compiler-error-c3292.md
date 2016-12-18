---
title: "Erreur du compilateur C3292 | Microsoft Docs"
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
  - "C3292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3292"
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3292
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de rouvrir l'espace de noms cli  
  
 L’espace de noms cli ne peut pas être déclaré dans votre code.  Pour plus d'informations, consultez [Platform, default, and cli Namespaces](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3292.  
  
```  
// C3292.cpp // compile with: /clr /c namespace cli {};   // C3292  
```