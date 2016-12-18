---
title: "Comment&#160;: d&#233;clarer des handles dans les types natifs | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot (mot clé C++)"
  - "handles, déclarer"
  - "types (C++), déclarer des handles dans"
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;clarer des handles dans les types natifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous ne pouvez pas déclarer un descripteur dans un type natif. vcclr.h fournit le modèle de type sécurisé `gcroot` de wrapper pour faire référence à un objet CLR du segment C\+\+.  Ce modèle vous permet d'incorporer un handle virtuel dans un type natif et de le traiter comme s'il était le type sous\-jacent.  Dans la plupart des cas, vous pouvez utiliser l'objet `gcroot` comme type incorporé sans conversion.  Toutefois, vous devez utiliser `static_cast` pour extraire la référence managée sous\-jacente avec [for each, in](../dotnet/for-each-in.md).  
  
 Le modèle `gcroot` est implémenté à l'aide des fonctionnalités de la classe value System::Runtime::InteropServices::GCHandle, qui fournit des « handles » dans le tas récupéré par le garbage collector.  Notez que les handles eux\-mêmes ne sont pas récupérés par le garbage collector et sont libérés lorsqu'ils ne sont plus utilisés par le destructeur dans la classe `gcroot` \(ce destructeur ne peut pas être appelé manuellement\).  Si vous instanciez un objet `gcroot` sur le tas natif, vous devez appeler delete sur cette ressource.  
  
 L'exécution maintiendra une association entre le handle et l'objet CLR qu'il référence.  Lorsque l'objet CLR est déplacé avec le tas récupéré par le garbage collector, le handle retourne la nouvelle adresse de l'objet.  Il n'est pas nécessaire qu'une variable soit épinglée avant d'être assignée à un modèle `gcroot`.  
  
## Exemple  
 Cet exemple montre comment créer un objet `gcroot` sur la pile native.  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
  **hello**   
## Exemple  
 Cet exemple montre comment créer un objet `gcroot` sur le tas natif.  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
  **hello**   
## Exemple  
 Cet exemple montre comment utiliser `gcroot` pour contenir des références à des types valeur \(et non des types référence\) dans un type natif en utilisant `gcroot` sur le type boxed.  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
  **String in V: Hello**   
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)