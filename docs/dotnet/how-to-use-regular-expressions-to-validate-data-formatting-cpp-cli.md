---
title: "Comment&#160;: valider la mise en forme de donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI) | Microsoft Docs"
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
  - "données (C++), mettre en forme"
  - "expressions régulières (C++), valider la mise en forme des données"
  - "chaînes (C++), mettre en forme"
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: valider la mise en forme de donn&#233;es &#224; l&#39;aide d&#39;expressions r&#233;guli&#232;res (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'utilisation d'expressions régulières pour vérifier la mise en forme d'une chaîne.  Dans l'exemple de code suivant, la chaîne doit contenir un numéro de téléphone valide.  L'exemple de code suivant utilise la chaîne "\\d{3}\-\\d{3}\-\\d{4}" pour indiquer que chaque champ représente un numéro de téléphone valide.  Le "d" dans la chaîne indique un chiffre, et l'argument situé après chaque "d" indique le nombre de chiffres qui doivent être présents.  Dans ce cas, le nombre doit être séparé par des tirets.  
  
## Exemple  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## Voir aussi  
 [Expressions régulières du .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)