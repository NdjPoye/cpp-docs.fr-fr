---
title: "Erreur du compilateur C3299 | Microsoft Docs"
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
  - "C3299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3299"
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_membre' : impossible de spécifier les contraintes, elles sont héritées de la méthode de base  
  
 Quand vous substituez une fonction membre générique, vous ne pouvez pas spécifier des clauses de contrainte \(car la répétition de contraintes sous\-entend que les contraintes ne sont pas héritées\).  
  
 Les clauses de contrainte de la fonction générique que vous substituez seront héritées.  
  
 Pour plus d'informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3299 :  
  
```  
// C3299.cpp // compile with: /clr /c public ref struct R { generic<class T> where T : R virtual void f(); }; public ref struct S : R { generic<class T> where T : R   // C3299 virtual void f() override; };  
```