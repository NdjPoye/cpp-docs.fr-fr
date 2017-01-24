---
title: "Comment&#160;: r&#233;cup&#233;rer le nom de l&#39;ordinateur local (C++/CLI) | Microsoft Docs"
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
  - "nom de l'ordinateur"
  - "nom de l'ordinateur, récupérer"
  - "nom de l'ordinateur, récupérer"
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: r&#233;cup&#233;rer le nom de l&#39;ordinateur local (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre la récupération du nom de l'ordinateur local \(nom de l'ordinateur tel qu'il apparaît sur un réseau\).  Vous pouvez effectuer cette opération en obtenant la chaîne <xref:System.Environment.MachineName%2A> qui est définie dans l'espace de noms <xref:System.Environment>.  
  
## Exemple  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)