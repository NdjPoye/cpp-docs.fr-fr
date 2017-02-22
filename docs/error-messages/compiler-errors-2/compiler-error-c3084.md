---
title: "Erreur du compilateur C3084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3084"
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C3084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : un finaliseur\/destructeur ne peut pas avoir la valeur 'keyword'  
  
 Un finaliseur ou un destructeur n’a pas été correctement déclaré.  
  
 Par exemple, un destructeur ne doit pas être marqué comme sealed.  Le destructeur sera inaccessible aux types dérivés.  Pour plus d’informations, consultez [Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md) et [Destructeurs et finaliseurs dans Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3084.  
  
```  
// C3084.cpp // compile with: /clr /c ref struct R { protected: !R() sealed;   // C3084 !R() abstract;   // C3084 !R(); };  
```