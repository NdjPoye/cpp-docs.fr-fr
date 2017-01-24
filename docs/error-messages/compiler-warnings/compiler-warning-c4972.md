---
title: "Avertissement du compilateur C4972 | Microsoft Docs"
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
  - "C4972"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4972"
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4972
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La modification ou le traitement direct du résultat d'une conversion unboxing comme lvalue est non vérifiable  
  
 Quand vous procédez au déréférencement d’un handle en un type valeur, \(également appelé « conversion unboxing »\), puis effectuez une assignation à celui\-ci, le résultat est non vérifiable.  
  
 Pour plus d'informations, consultez [Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C4972.  
  
```  
// C4972.cpp // compile with: /clr:safe using namespace System; ref struct R { int ^ p;   // a value type }; int main() { R ^ r = gcnew R; *(r->p) = 10;   // C4972 // OK r->p = 10; Console::WriteLine( r->p ); Console::WriteLine( *(r->p) ); }  
```