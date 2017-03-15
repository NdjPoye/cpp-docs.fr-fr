---
title: "Comment&#160;: sp&#233;cifier un param&#232;tre Out | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "paramètres de fonction"
  - "out (paramètres)"
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Comment&#160;: sp&#233;cifier un param&#232;tre Out
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet exemple indique comment spécifier qu'un paramètre de fonction est un paramètre de sortie et comment appeler cette fonction à partir d'un programme C\#.  
  
 En Visual C\+\+, un paramètre de sortie est spécifié avec <xref:System.Runtime.InteropServices.OutAttribute>.  
  
## Exemple  
 La première partie de cet exemple est une DLL Visual C\+\+ possédant un type qui contient une fonction avec un paramètre de sortie.  
  
```  
// cpp_out_param.cpp  
// compile with: /LD /clr:safe  
using namespace System;  
public value struct TestStruct {  
   static void Test([Runtime::InteropServices::Out] String^ %s) {  
      s = "a string";  
   }  
};  
```  
  
## Exemple  
 Il s'agit d'un client C\# qui consomme le composant Visual C\+\+ créé dans l'exemple précédent.  
  
```  
// cpp_out_param_2.cs  
// compile with: /reference:cpp_out_param.dll  
using System;  
class TestClass {  
   public static void Main() {  
      String t;  
      TestStruct.Test(out t);  
      System.Console.WriteLine(t);  
   }  
}  
```  
  
  **a string**   
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)