---
title: "Erreur du compilateur C3237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3237"
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'generic\_class' : une classe générique ne peut pas être un attribut personnalisé  
  
 Les classes génériques ne peuvent pas être des attributs définis par l’utilisateur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3237.  
  
```  
// C3237.cpp // compile with: /clr /c // C3237 expected using namespace System; generic <class T> // Delete the following line to resolve. [attribute(AttributeTargets::All, AllowMultiple=true)] public ref class GR {};  
```