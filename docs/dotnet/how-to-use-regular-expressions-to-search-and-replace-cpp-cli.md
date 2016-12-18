---
title: "Comment&#160;: utiliser des expressions r&#233;guli&#232;res pour les recherches et remplacements (C++/CLI) | Microsoft Docs"
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
  - "expressions régulières (C++), rechercher et remplacer"
  - "Replace (méthode)"
  - "rechercher et remplacer"
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser des expressions r&#233;guli&#232;res pour les recherches et remplacements (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment la classe d'expressions régulières <xref:System.Text.RegularExpressions.Regex> peut être utilisée pour effectuer une opération de recherche et de remplacement.  Pour cela, vous devez utiliser la méthode <xref:System.Text.RegularExpressions.Regex.Replace%2A>.  La version utilisée prend deux chaînes comme entrée : la chaîne à modifier et la chaîne à insérer à la place des sections \(éventuelles\) qui correspondent au motif donné à l'objet <xref:System.Text.RegularExpressions.Regex>.  
  
 Ce code remplace tous les chiffres d'une chaîne par des traits de soulignement \(\_\), puis remplace les chaînes vides en les supprimant réellement.  Le même effet peut être obtenu en une seule étape, mais deux étapes sont utilisées ici à des fins de démonstration.  
  
## Exemple  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)