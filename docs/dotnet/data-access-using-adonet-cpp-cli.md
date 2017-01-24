---
title: "Acc&#232;s aux donn&#233;es &#224; l&#39;aide d&#39;ADO.NET (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework (C++), accès aux données"
  - "ADO.NET (C++)"
  - "données (C++), ADO.NET"
  - "accès aux données (C++), ADO.NET"
  - "bases de données (C++), accéder en C++"
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s aux donn&#233;es &#224; l&#39;aide d&#39;ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ADO.NET est l'API du .NET Framework permettant d'accéder aux données ; elle offre une puissance et une facilité d'utilisation jamais atteinte par les précédentes solutions d'accès aux données.  Cette section décrit quelques\-uns des problèmes impliquant ADO.NET qui ne concernent que les utilisateurs Visual C\+\+, par exemple marshaler des types natifs.  
  
 ADO.NET s'exécute sous le Common Language Runtime \(CLR\).  Par conséquent, toute application qui interagit avec ADO.NET doit également cibler le CLR.  Toutefois, cela ne signifie pas que les applications natives ne peuvent pas utiliser ADO.NET.  Ces exemples montreront comment interagir avec une base de données ADO.NET depuis le code natif.  
  
## Dans cette section  
 [Comment : marshaler des chaînes ANSI pour ADO.NET](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Comment : marshaler des chaînes BSTR pour ADO.NET](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Comment : marshaler des chaînes Unicode pour ADO.NET](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Comment : marshaler un VARIANT pour ADO.NET](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Comment : marshaler un SAFEARRAY pour ADO.NET](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## Rubriques connexes  
  
|Section|Description|  
|-------------|-----------------|  
|[ADO.NET](../Topic/ADO.NET.md)|Fournit une vue d'ensemble d'ADO.NET, ensemble de classes qui exposent des services d'accès aux données au programmeur .NET.|  
|[Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/fr-fr/5358a825-e19b-49aa-8214-674ce5fed1da)|Décrit comment utiliser les langages .NET, y compris Visual C\+\+, pour créer des objets de base de données, tels que procédures stockées, agrégats, déclencheurs, fonctions définies par l'utilisateur et types définis par l'utilisateur ; décrit aussi comment récupérer et mettre à jour les données pour les bases de données Microsoft SQL Server 2005.|  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)