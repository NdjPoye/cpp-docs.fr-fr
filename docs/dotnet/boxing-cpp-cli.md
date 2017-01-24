---
title: "Boxing (C++/CLI) | Microsoft Docs"
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
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Boxing (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Boxing is the process of converting a value type to the type `object` or to any interface type that's implemented by the value type.  When the common language runtime \(CLR\) boxes a value type, it wraps the value in a `System.Object` and stores it on the managed heap.  L'unboxing extrait le type valeur de l'objet.  La conversion boxing est implicite ; la conversion unboxing est explicite.  
  
## Articles connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Comment : demander explicitement le boxing](../dotnet/how-to-explicitly-request-boxing.md)|Describes how to explicitly request boxing on a variable.|  
|[Comment : utiliser gcnew pour créer des types de valeur et utiliser un boxing implicite](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Shows how to use `gcnew` to create a boxed value type that can be placed on the managed, garbage\-collected heap.|  
|[Comment : effectuer une conversion unbox](../dotnet/how-to-unbox.md)|Shows how to unbox and modify a value.|  
|[Conversions standard et boxing implicite](../dotnet/standard-conversions-and-implicit-boxing.md)|Shows that a standard conversion is chosen by the compiler over a conversion that requires boxing.|  
|[Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|The top\-level article for .NET programming in the Visual C\+\+ documentation.|