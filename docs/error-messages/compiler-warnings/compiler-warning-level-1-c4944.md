---
title: "Avertissement du compilateur (niveau&#160;1) C4944 | Microsoft Docs"
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
  - "C4944"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4944"
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4944
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : impossible d’importer le symbole de 'assembly1', car 'symbole' existe déjà dans la portée actuelle  
  
 Un symbole a été défini dans un fichier de code source, puis une instruction \#using a référencé un assembly définissant également le symbole. Le symbole contenu dans l’assembly est ignoré.  
  
## Exemple  
 Dans l’exemple suivant, un composant est créé avec un type appelé ClassA.  
  
```  
// C4944.cs // compile with: /target:library // C# source code to create a dll public class ClassA { public int i; }  
```  
  
## Exemple  
 Les exemples suivants génèrent l’erreur C4944.  
  
```  
// C4944b.cpp // compile with: /clr /W1 class ClassA { public: int u; }; #using "C4944.dll"   // C4944 ClassA also defined C4944.dll int main() { ClassA * x = new ClassA(); x->u = 9; System::Console::WriteLine(x->u); }  
```