---
title: "Comment&#160;: marshaler des cha&#238;nes Unicode &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interopérabilité C++, chaînes"
  - "marshaling de données (C++), chaînes"
  - "Interop (C++), chaînes"
  - "marshaling (C++), chaînes"
  - "Unicode, marshaler des chaînes"
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des cha&#238;nes Unicode &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique illustre une facette de l'interopérabilité Visual C\+\+.  Pour plus d'informations, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais ces fonctions interagissent de la même manière si elles sont définies dans des fichiers séparés.  Les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Cette rubrique montre comment les chaînes Unicode peuvent être passées d'une fonction managée à une fonction non managée, et inversement.  Pour interagir avec d'autres types de chaînes, consultez les rubriques suivantes :  
  
-   [Comment : marshaler des chaînes ANSI à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des chaînes COM à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## Exemple  
 Pour passer une chaîne Unicode d'une fonction managée à une fonction non managée, la fonction PtrToStringChars \(déclarée dans Vcclr.h\) peut être utilisée afin d'accéder à la mémoire où la chaîne managée est stockée.  Comme cette adresse sera passée à une fonction native, il est important que la mémoire soit épinglée avec [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) pour empêcher le réadressage des données de type chaîne au cas où un cycle de garbage collection se produirait pendant l'exécution de la fonction non managée.  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## Exemple  
 L'exemple suivant illustre le marshaling de données nécessaire pour accéder à une chaîne Unicode dans une fonction managée appelée par une fonction non managée.  Lorsqu'elle reçoit la chaîne Unicode native, la fonction managée la convertit en chaîne managée à l'aide de la méthode <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A>.  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)