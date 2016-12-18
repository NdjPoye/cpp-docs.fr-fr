---
title: "Comment&#160;: &#233;tablir des correspondances simples &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI) | Microsoft Docs"
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
  - "IsMatch (méthode)"
  - "expressions régulières (C++), correspondance simple"
  - "rechercher, correspondances de sous-chaînes exactes"
  - "chaînes (C++), correspondances de sous-chaînes exactes"
  - "sous-chaînes, correspondances simples"
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;tablir des correspondances simples &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise des expressions régulières pour rechercher des correspondances de sous\-chaînes exactes.  La recherche est exécutée par la méthode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> statique qui prend deux chaînes comme entrée.  La première est la chaîne à rechercher et la deuxième est le motif à rechercher.  
  
## Exemple  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)