---
title: "Accès aux données en utilisant ADO.NET (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fb7d184ebdb537c02b79a412d69a4bdcaabde424
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="data-access-using-adonet-ccli"></a>Accès aux données à l'aide d'ADO.NET (C++/CLI)
ADO.NET est l’API .NET Framework pour accéder aux données et fournit la puissance et la simplicité d’utilisation sans correspondance par les solutions d’accès aux données précédente. Cette section décrit certains des problèmes impliquant ADO.NET qui sont propres aux utilisateurs de Visual C++, telles que le marshaling des types natifs.  
  
 ADO.NET s’exécute sous le Common Language Runtime (CLR). Par conséquent, toute application qui interagit avec ADO.NET doit également cibler le CLR. Toutefois, cela ne signifie pas que les applications natives ne peuvent pas utiliser ADO.NET. Ces exemples montreront comment interagir avec une base de données ADO.NET à partir du code natif.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Guide pratique pour marshaler des chaînes ANSI pour ADO.NET (C++-CLI)](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Guide pratique pour marshaler des chaînes BSTR pour ADO.NET (C++-CLI)](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Guide pratique pour marshaler des chaînes Unicode pour ADO.NET (C++-CLI)](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Guide pratique pour marshaler un VARIANT pour ADO.NET (C++-CLI)](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Guide pratique pour marshaler un SAFEARRAY pour ADO.NET (C++-CLI)](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## <a name="related-sections"></a>Rubriques connexes  
  
|Section|Description|  
|-------------|-----------------|  
|[ADO.NET](/dotnet/framework/data/adonet/index)|Fournit une vue d’ensemble d’ADO.NET, un ensemble de classes qui exposent des services d’accès aux données au programmeur .NET.|  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation .NET avec c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)