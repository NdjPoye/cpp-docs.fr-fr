---
title: "Comment&#160;: convertir une cha&#238;ne standard en System::String | Microsoft Docs"
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
  - "bibliothèque C++ standard, convertir des chaînes en System::String"
  - "conversion de chaînes (C++), chaîne de la bibliothèque C++ standard"
  - "chaînes (C++), convertir"
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Comment&#160;: convertir une cha&#238;ne standard en System::String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit comment convertir une chaîne de bibliothèque C\+\+ standard \([\<string\>](../standard-library/string.md)\) en <xref:System.String>.  
  
## Exemple  
  
```  
// convert_standard_string_to_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace System;  
using namespace std;  
  
int main() {  
   string str = "test";  
   cout << str << endl;  
   String^ str2 = gcnew String(str.c_str());  
   Console::WriteLine(str2);  
  
   // alternatively  
   String^ str3 = gcnew String(str.c_str());  
   Console::WriteLine(str3);  
}  
```  
  
  **tester**  
**tester**  
**tester**   
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)