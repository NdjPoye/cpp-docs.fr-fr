---
title: "Comment&#160;: analyser des cha&#238;nes &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI) | Microsoft Docs"
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
  - "chaînes (C++), analyser"
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: analyser des cha&#238;nes &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'analyse d'une chaîne simple à l'aide de la classe <xref:System.Text.RegularExpressions.Regex> dans l'espace de noms <xref:System.Text.RegularExpressions?displayProperty=fullName>.  Une chaîne contenant plusieurs types de délinéateurs de mots est créée.  Elle est analysée à l'aide de la classe <xref:System.Text.RegularExpressions.Regex> conjointement avec la classe <xref:System.Text.RegularExpressions.Match>.  Ensuite, chaque mot de la phrase est affiché séparément.  
  
## Exemple  
  
```  
// regex_parse.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main( )  
{  
   int words = 0;  
   String^ pattern = "[a-zA-Z]*";  
   Console::WriteLine( "pattern : '{0}'", pattern );  
   Regex^ regex = gcnew Regex( pattern );  
  
   String^ line = "one\ttwo three:four,five six  seven";     
   Console::WriteLine( "text : '{0}'", line );  
   for( Match^ match = regex->Match( line );   
        match->Success; match = match->NextMatch( ) )   
   {  
      if( match->Value->Length > 0 )  
      {  
         words++;  
         Console::WriteLine( "{0}", match->Value );  
      }  
   }  
   Console::WriteLine( "Number of Words : {0}", words );  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)