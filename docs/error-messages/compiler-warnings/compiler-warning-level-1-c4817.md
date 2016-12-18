---
title: "Avertissement du compilateur (niveau&#160;1) C4817 | Microsoft Docs"
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
  - "C4817"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4817"
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4817
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : utilisation non conforme de '.' pour accéder à ce membre ; compilateur remplacé par '\-\>'  
  
 Le mauvais opérateur d’accès aux membres a été utilisé.  
  
## Exemple  
 L’exemple suivant génère l’erreur C4817 :  
  
```  
// C4817.cpp // compile with: /clr /W1 using namespace System; int main() { array<Int32> ^ a = gcnew array<Int32>(100); Console::WriteLine( a.Length );   // C4817 Console::WriteLine( a->Length );   // OK }  
```  
  
## Exemple  
 L’erreur C4817 peut également être générée si vous utilisez **\/clr:oldSyntax**. L’exemple suivant génère l’erreur C4817 :  
  
```  
// C4817_b.cpp // compile with: /clr:oldSyntax /W1 using namespace System; int main() { Int32 a[] = new Int32[11]; Console::WriteLine( a.Length ); // Console::WriteLine( a->Length ); }  
```