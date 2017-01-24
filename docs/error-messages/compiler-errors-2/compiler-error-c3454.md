---
title: "Erreur du compilateur C3454 | Microsoft Docs"
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
  - "C3454"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3454"
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3454
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[attribute\] non autorisé dans une déclaration de classe  
  
 Pour être un attribut, une classe doit être définie.  
  
 Pour plus d'informations, consultez [attribute](../../windows/attribute.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3454 :  
  
```  
// C3454.cpp // compile with: /clr /c using namespace System; [attribute]   // C3454 ref class Attr1; [attribute]   // OK ref class Attr2 {};  
```