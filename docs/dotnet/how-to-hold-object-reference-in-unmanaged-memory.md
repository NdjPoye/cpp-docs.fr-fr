---
title: "Comment&#160;: stocker la r&#233;f&#233;rence d&#39;un objet dans une m&#233;moire non manag&#233;e | Microsoft Docs"
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
  - "gcroot (mot clé C++), référence d'objet dans une fonction native"
  - "références d'objet, dans des fonctions natives"
  - "objets (C++), référence dans des fonctions natives"
  - "références, à des objets dans des fonctions natives"
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Comment&#160;: stocker la r&#233;f&#233;rence d&#39;un objet dans une m&#233;moire non manag&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser gcroot.h, qui encapsule <xref:System.Runtime.InteropServices.GCHandle>, pour stocker une référence d'objet du CLR dans la mémoire non managée.  Vous pouvez aussi utiliser directement `GCHandle`.  
  
## Exemple  
  
```  
// hold_object_reference.cpp  
// compile with: /clr  
#include "gcroot.h"  
using namespace System;  
  
#pragma managed  
class StringWrapper {  
  
private:  
   gcroot<String ^ > x;  
  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      x = str;  
   }  
  
   void PrintString() {  
      String ^ targetStr = x;  
      Console::WriteLine("StringWrapper::x == {0}", targetStr);  
   }  
};  
#pragma unmanaged  
int main() {  
   StringWrapper s;  
   s.PrintString();  
}  
```  
  
  **StringWrapper::x \=\= ManagedString**   
## Exemple  
 `GCHandle` vous donne un moyen de stocker une référence d'objet managé dans la mémoire non managée.  Vous pouvez utiliser la méthode <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> pour créer un handle opaque vers un objet managé et <xref:System.Runtime.InteropServices.GCHandle.Free%2A> pour le libérer.  En outre, la méthode <xref:System.Runtime.InteropServices.GCHandle.Target%2A> vous permet de récupérer la référence de l'objet à partir du handle dans du code managé.  
  
```  
// hold_object_reference_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
class StringWrapper {  
   IntPtr m_handle;  
public:  
   StringWrapper() {  
      String ^ str = gcnew String("ManagedString");  
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));  
   }  
   ~StringWrapper() {  
      static_cast<GCHandle>(m_handle).Free();  
   }  
  
   void PrintString() {  
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);  
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);  
   }  
};  
  
#pragma unmanaged  
int main() {  
   StringWrapper s;   
   s.PrintString();  
}  
```  
  
  **StringWrapper::m\_handle \=\= ManagedString**   
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)