---
title: "Erreur du compilateur C2474 | Microsoft Docs"
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
  - "C2474"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2474"
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2474
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' : point\-virgule adjacent manquant ; il peut s’agir d’un mot clé ou d’un identificateur.  
  
 Le compilateur attendait un point\-virgule et n’a pas pu identifier ce que vous souhaitiez faire. Ajoutez le point\-virgule pour résoudre cette erreur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2474.  
  
```  
// C2474.cpp // compile with: /clr /c ref class A { ref class B {} property int i;   // C2474 error }; // OK ref class B { ref class D {}; property int i; }; ref class E { ref class F {} property; int i; };  
```