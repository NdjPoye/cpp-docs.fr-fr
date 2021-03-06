---
title: 'Comment : marshaler des rappels et délégués à l’aide d’interopérabilité C++ | Documents Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd1b9a13ebcc9f416a2953f53c98231b7a0df3c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>Comment : marshaler des rappels et des délégués à l’aide de l’interopérabilité C++
Cette rubrique illustre le marshaling de rappels et délégués (version managée d’un rappel) entre du code managé et à l’aide de Visual C++.  
  
 Exemple de code suit le [managé, non managé](../preprocessor/managed-unmanaged.md) directives #pragma pour implémenter des fonctions managées et dans le même fichier, mais les fonctions peuvent également être définies dans des fichiers distincts. Fichiers contenant uniquement des fonctions non managées ne doivent pas être compilés avec le [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer une API non managée pour déclencher un délégué managé. Un délégué managé est créé et l’une des méthodes d’interopérabilité, <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>, est utilisée pour récupérer le point d’entrée sous-jacent du délégué. Cette adresse est ensuite passée à la fonction non managée, ce qui l’appelle aucune connaissance du fait qu’il est implémenté comme une fonction managée.  
  
 Remarquez qu’il est possible, mais pas nécessaire, d’épingler le délégué à l’aide de [pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md) empêcher d’être réadressé ou supprimé par le garbage collector. Protection contre les garbage collection prématuré est nécessaire, mais épinglage assure une protection plus qu’il n’est nécessaire, car elle empêche la collection, mais empêche également le déplacement.  
  
 Si un délégué est réadressé par un garbage collection, il n’affecte pas du rappel managé sous-jacent, donc <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> est utilisé pour ajouter une référence au délégué, ce qui permet de réadressage du délégué, mais empêche la suppression. L’utilisation de GCHandle plutôt que de pin_ptr de réduit le risque de fragmentation du tas managé.  
  
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
  
## <a name="example"></a>Exemple  
 L’exemple suivant est similaire à l’exemple précédent, mais dans ce cas le pointeur de fonction fourni est stocké par l’API non managée, afin qu’il peut être appelée à tout moment, nécessitant que le garbage collection supprimées pendant une durée arbitraire. Par conséquent, l’exemple suivant utilise une instance globale de <xref:System.Runtime.InteropServices.GCHandle> pour empêcher le délégué d’être réadressé, indépendamment de la portée de la fonction. Comme indiqué dans le premier exemple, à l’aide de pin_ptr n’est pas nécessaire pour ces exemples, mais dans ce cas ne fonctionnerait pas, car la portée de pin_ptr est limitée à une fonction unique.  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de l’interopérabilité C++ (PInvoke implicite)](../dotnet/using-cpp-interop-implicit-pinvoke.md)