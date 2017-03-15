---
title: "Comment&#160;: d&#233;terminer si le processus d&#39;arr&#234;t a commenc&#233; (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework, arrêt"
  - "applications (C++), arrêt"
  - "arrêt"
  - "arrêt"
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;terminer si le processus d&#39;arr&#234;t a commenc&#233; (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment déterminer si l'application ou le .NET Framework se referment actuellement.  Cela peut être utile pour accéder aux éléments statiques dans le .NET Framework. En effet, pendant l'arrêt, ces constructions sont finalisées par le système et ne peuvent pas être utilisées de manière fiable.  Vous pouvez vérifier d'abord la propriété <xref:System.Environment.HasShutdownStarted%2A> afin d'éviter des défaillances potentielles en n'accédant pas à ces éléments.  
  
## Exemple  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)