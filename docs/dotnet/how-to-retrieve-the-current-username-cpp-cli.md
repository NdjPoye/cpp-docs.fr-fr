---
title: "Comment&#160;: r&#233;cup&#233;rer le nom d&#39;utilisateur actuel (C++/CLI) | Microsoft Docs"
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
  - "noms d'utilisateurs actuels"
  - "noms d'utilisateurs, récupérer"
  - "UserName (chaîne)"
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: r&#233;cup&#233;rer le nom d&#39;utilisateur actuel (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre la récupération du nom d'utilisateur actuel \(nom de l'utilisateur enregistré dans Windows\).  Le nom est stocké dans la chaîne <xref:System.Environment.UserName%2A> qui est définie dans l'espace de noms <xref:System.Environment>.  
  
## Exemple  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)