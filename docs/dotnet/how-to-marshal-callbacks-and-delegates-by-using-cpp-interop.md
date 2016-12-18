---
title: "Comment&#160;: marshaler des rappels et des d&#233;l&#233;gu&#233;s &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++ | Microsoft Docs"
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
  - "interopérabilité C++, rappels et délégués"
  - "rappels (C++), marshaling"
  - "marshaling de données (C++), rappels et délégués"
  - "délégués (C++), marshaling"
  - "Interop (C++), rappels et délégués"
  - "marshaling (C++), rappels et délégués"
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des rappels et des d&#233;l&#233;gu&#233;s &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233;&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique illustre le marshaling de rappels et de délégués \(version managée d'un rappel\) entre du code managé et non managé à l'aide de Visual C\+\+.  
  
 Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais les fonctions peuvent également être définies dans des fichiers séparés.  Les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant illustre la configuration d'une API non managée pour déclencher un délégué managé.  Un délégué managé est créé et l'une des méthodes d'interopérabilité, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, est utilisée pour récupérer le point d'entrée sous\-jacent du délégué.  Cette adresse est ensuite passée à la fonction non managée qui l'appelle sans avoir connaissance du fait qu'elle est implémentée en tant que fonction managée.  
  
 Remarquez qu'il est possible, mais pas nécessaire, d'épingler le délégué à l'aide de [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) pour l'empêcher d'être réadressé ou supprimé par le garbage collector.  La protection contre un garbage collection prématuré est exigée, mais l'épinglage assure une protection plus élevée que ce qui est requis, car il empêche la collecte, mais également le réadressage.  
  
 Si un délégué est réadressé par un garbage collection, il n'affecte pas le rappel managé sous\-jacent ; <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> est donc utilisé pour ajouter une référence au délégué, en autorisant le réadressage du délégué, mais en empêchant sa suppression.  L'utilisation de GCHandle plutôt que de pin\_ptr réduit le potentiel de fragmentation du tas managé.  
  
```  
// MarshalDelegate1.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n, m);  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   return n + m;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   GCHandle gch = GCHandle::Alloc(fp);  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
// force garbage collection cycle to prove  
// that the delegate doesn't get disposed  
   GC::Collect();  
  
   int answer = TakesCallback(cb, 243, 257);  
  
// release reference to delegate  
   gch.Free();  
}  
```  
  
## Exemple  
 L'exemple suivant est similaire à l'exemple précédent, mais dans ce cas, le pointeur fonction fourni est stocké par l'API non managée ; il peut donc être appelé à tout moment, en exigeant la suppression du garbage collection pendant une durée arbitraire.  En conséquence, l'exemple suivant utilise une instance globale de <xref:System.Runtime.InteropServices.GCHandle> pour empêcher le délégué d'être réadressé, indépendamment de la portée de la fonction.  Comme expliqué dans le premier exemple, l'utilisation de pin\_ptr est inutile pour ces exemples, mais s'avère de toute manière inutile dans ce cas précis, car la portée de pin\_ptr est limitée à une fonction unique.  
  
```  
// MarshalDelegate2.cpp  
// compile with: /clr   
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
static ANSWERCB cb;  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   cb = fp;  
   if (cb) {  
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);  
      return cb(n, m);  
   }  
   printf_s("[unmanaged] unregistering callback");  
   return 0;  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
  
   return n + m + x;  
}  
  
static GCHandle gch;  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
  
   gch = GCHandle::Alloc(fp);  
  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TakesCallback(cb, 243, 257);  
  
   // possibly much later (in another function)...  
  
   Console::WriteLine("[managed] releasing callback mechanisms...");  
   TakesCallback(0, 243, 257);  
   gch.Free();  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)