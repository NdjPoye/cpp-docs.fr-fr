---
title: "Avertissement du compilateur C4694 | Microsoft Docs"
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
  - "C4694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4694"
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class\_1' : une classe abstraite sealed ne peut pas avoir de classe de base 'base\_class'  
  
 Une classe abstraite et sealed ne peut pas hériter d’un type référence ; elle ne peut pas non plus implémenter de fonctions de classe de base ou se laisser utiliser comme classe de base.  
  
 Pour plus d'informations, consultez [abstract](../../windows/abstract-cpp-component-extensions.md), [sealed](../../windows/sealed-cpp-component-extensions.md) et [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4694.  
  
```  
// C4694.cpp // compile with: /c /clr ref struct A {}; ref struct B sealed abstract : A {};   // C4694  
```