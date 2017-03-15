---
title: "Comment&#160;: r&#233;organiser des donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI) | Microsoft Docs"
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
  - "données (C++), réorganiser"
  - "expressions régulières (C++), réorganiser les données"
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: r&#233;organiser des donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment la prise en charge des expressions régulières du .NET Framework peut être utilisée pour réorganiser ou reformater des données.  L'exemple de code suivant utilise les classes <xref:System.Text.RegularExpressions.Regex> et <xref:System.Text.RegularExpressions.Match> pour extraire les prénoms et noms d'une chaîne, puis afficher ces éléments dans l'ordre inverse.  
  
 La classe <xref:System.Text.RegularExpressions.Regex> est utilisée pour construire une expression régulière qui décrit le format actuel des données.  Les deux noms sont supposés être séparés par une virgule et peuvent utiliser n'importe quel nombre d'espaces blancs autour de la virgule.  La méthode <xref:System.Text.RegularExpressions.Match> est ensuite utilisée pour analyser chaque chaîne.  En cas de réussite, les prénoms et noms sont récupérés à partir de l'objet <xref:System.Text.RegularExpressions.Match> et sont affichés.  
  
## Exemple  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)