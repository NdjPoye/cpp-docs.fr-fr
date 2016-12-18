---
title: "Comment&#160;: analyser des cha&#238;nes &#224; l&#39;aide de la m&#233;thode Split (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exemples (C++), chaînes"
  - "analyser des chaînes (C++)"
  - "expressions régulières (C++), analyser des chaînes"
  - "Split (méthode), analyser des chaînes"
  - "chaînes (C++), analyser"
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: analyser des cha&#238;nes &#224; l&#39;aide de la m&#233;thode Split (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'utilisation de la méthode <xref:System.String.Split%2A?displayProperty=fullName> pour extraire chaque mot d'une chaîne.  Une chaîne qui contient plusieurs types de délinéateurs de mots est construite, puis analysée en appelant <xref:System.String.Split%2A> avec la liste des délinéateurs.  Ensuite, chaque mot de la phrase est affiché séparément.  
  
## Exemple  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)