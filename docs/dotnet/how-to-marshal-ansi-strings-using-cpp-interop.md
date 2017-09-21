---
title: "Comment&#160;: marshaler des cha&#238;nes ANSI &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++ | Microsoft Docs"
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
  - "ANSI (C++), marshaler des chaînes"
  - "interopérabilité C++, chaînes"
  - "marshaling de données (C++), chaînes"
  - "Interop (C++), chaînes"
  - "marshaling (C++), chaînes"
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des cha&#238;nes ANSI &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique montre comment les chaînes ANSI peuvent être passées à l'aide de C\+\+ Interop, mais le <xref:System.String> du .NET Framework représente des chaînes au format Unicode. Par conséquent, une étape supplémentaire est requise pour la conversion au format ANSI.  Pour interagir avec d'autres types de chaînes, consultez les rubriques suivantes :  
  
-   [Comment : marshaler des chaînes Unicode à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des chaînes COM à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais ces fonctions interagissent de la même manière si elles sont définies dans des fichiers séparés.  Comme les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md), ils peuvent conserver leurs caractéristiques de performances.  
  
## Exemple  
 Cet exemple illustre le passage d'une chaîne ANSI d'une fonction managée à une fonction non managée à l'aide de <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>.  Cette méthode alloue de la mémoire sur le tas non managé et retourne l'adresse une fois la conversion exécutée.  Cela signifie qu'aucun épinglage n'est nécessaire \(car la mémoire sur le tas GC n'est pas passée à la fonction non managée\) et que la valeur IntPtr retournée par <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> doit être libérée explicitement sous peine d'entraîner une fuite de mémoire.  
  
```  
// MarshalANSI1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const char* p) {  
   printf_s("(native) received '%s'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("sample string");  
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);  
   const char* str = static_cast<const char*>(ip.ToPointer());  
  
   Console::WriteLine("(managed) passing string...");  
   NativeTakesAString( str );  
  
   Marshal::FreeHGlobal( ip );  
}  
```  
  
## Exemple  
 L'exemple suivant illustre le marshaling de données nécessaire pour accéder à une chaîne ANSI dans une fonction managée appelée par une fonction non managée.  Lors de la réception de la chaîne native, la fonction managée peut l'utiliser directement ou la convertir en chaîne managée à l'aide de la méthode <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A>, comme indiqué.  
  
```  
// MarshalANSI2.cpp  
// compile with: /clr  
#include <iostream>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(char* s) {  
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));  
   Console::WriteLine("(managed): received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(native) calling managed func...\n";  
   ManagedStringFunc("test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)