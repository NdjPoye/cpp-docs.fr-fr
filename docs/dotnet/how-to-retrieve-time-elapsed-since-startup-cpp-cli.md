---
title: "Comment&#160;: r&#233;cup&#233;rer le temps &#233;coul&#233; depuis le d&#233;marrage (C++/CLI) | Microsoft Docs"
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
  - "compteurs, temps écoulé"
  - "démarrage"
  - "démarrage, temps écoulé depuis"
  - "nombres de cycles"
  - "heure, temps écoulé depuis le démarrage"
ms.assetid: a31fdecc-099e-4dd1-a176-f682289c5dd0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: r&#233;cup&#233;rer le temps &#233;coul&#233; depuis le d&#233;marrage (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment déterminer le nombre de tics ou le nombre des millisecondes qui se sont écoulées depuis le démarrage de Windows.  Cette valeur est stockée dans le membre <xref:System.Environment.TickCount%2A?displayProperty=fullName> et, comme il s'agit d'une valeur de 32 bits, elle est remise à zéro tous les 24,9 jours environ.  
  
## Exemple  
  
```  
// startup_time.cpp  
// compile with: /clr  
using namespace System;  
  
int main( )   
{  
   Int32 tc = Environment::TickCount;  
   Int32 seconds = tc / 1000;  
   Int32 minutes = seconds / 60;  
   float hours = static_cast<float>(minutes) / 60;  
   float days = hours / 24;  
  
   Console::WriteLine("Milliseconds since startup: {0}", tc);  
   Console::WriteLine("Seconds since startup: {0}", seconds);  
   Console::WriteLine("Minutes since startup: {0}", minutes);  
   Console::WriteLine("Hours since startup: {0}", hours);  
   Console::WriteLine("Days since startup: {0}", days);  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)