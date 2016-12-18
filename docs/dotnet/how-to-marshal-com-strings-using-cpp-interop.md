---
title: "Comment&#160;: marshaler des cha&#238;nes COM &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++ | Microsoft Docs"
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
  - "COM (C++), marshaler des chaînes"
  - "marshaling de données (C++), chaînes"
  - "Interop (C++), chaînes"
  - "marshaling (C++), chaînes"
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des cha&#238;nes COM &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique montre comment un BSTR \(format de chaîne de base favorisé dans la programmation COM\) peut être passé d'une fonction managée à une fonction non managée, et inversement.  Pour interagir avec d'autres types de chaînes, consultez les rubriques suivantes :  
  
-   [Comment : marshaler des chaînes Unicode à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Comment : marshaler des chaînes ANSI à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais ces fonctions interagissent de la même manière si elles sont définies dans des fichiers séparés.  Les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant montre comment un BSTR \(format de chaîne utilisé dans la programmation COM\) peut être passé d'une fonction managée à une fonction non managée.  La fonction managée appelante utilise <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> pour obtenir l'adresse d'une représentation BSTR du contenu d'un .NET System.String.  Ce pointeur est épinglé à l'aide de [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) pour vérifier que son adresse physique n'est pas modifiée pendant un cycle de garbage collection au cours de l'exécution de la fonction non managée.  Le garbage collector n'est pas autorisé à déplacer la mémoire aussi longtemps que [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) n'est pas hors de portée.  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## Exemple  
 L'exemple suivant montre comment un BSTR peut être passé d'une fonction non managée à une fonction non managée.  La fonction managée réceptrice peut utiliser la chaîne en tant que BSTR ou utiliser <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> pour la convertir en <xref:System.String> en vue d'une utilisation avec d'autres fonctions managées.  Comme la mémoire représentant le BSTR est allouée sur le tas non managé, aucun épinglage n'est nécessaire, car il n'existe aucun garbage collection sur le tas non managé.  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)