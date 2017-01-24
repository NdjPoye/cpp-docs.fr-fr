---
title: "Comment&#160;: d&#233;terminer l&#39;&#233;tat interactif d&#39;un utilisateur (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "état interactif des utilisateurs"
  - "Visual C++, état interactif des utilisateurs"
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;terminer l&#39;&#233;tat interactif d&#39;un utilisateur (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment déterminer si le code s'exécute dans un contexte interactif de l'utilisateur.  Si <xref:System.Environment.UserInteractive%2A> a la valeur false, le code s'exécute en tant que processus de service ou à partir de l'intérieur d'une application Web ; dans ce cas, vous ne devez pas tenter d'interagir avec l'utilisateur.  
  
## Exemple  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)