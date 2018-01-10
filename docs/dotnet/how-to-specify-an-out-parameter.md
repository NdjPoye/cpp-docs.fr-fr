---
title: "Comment : spécifier une attente paramètre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0905220a1e2ab3e209fe80598ec67903999245b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-specify-an-out-parameter"></a>Comment : spécifier un paramètre Out
Cet exemple montre comment spécifier qu’un paramètre de fonction est un paramètre de sortie et comment appeler cette fonction à partir d’un programme c#.  
  
 Un paramètre de sortie est spécifié dans Visual C++ avec <xref:System.Runtime.InteropServices.OutAttribute> .  
  
## <a name="example"></a>Exemple  
 La première partie de cet exemple est une DLL Visual C++ avec un type qui contient une fonction avec un paramètre de sortie.  
  
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
  
## <a name="example"></a>Exemple  
 Il s’agit d’un client c# qui consomme le composant Visual C++ créé dans l’exemple précédent.  
  
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
  
```Output  
a string  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de l’interopérabilité C++ (PInvoke implicite)](../dotnet/using-cpp-interop-implicit-pinvoke.md)