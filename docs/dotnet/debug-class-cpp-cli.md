---
title: Debug (classe) (C + c++ / CLI) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 14354241c4e16e1177a5680b901a738f16036f96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="debug-class-ccli"></a>Classe de débogage (C++/CLI)
Lorsque vous utilisez <xref:System.Diagnostics.Debug> dans une application Visual C++, le comportement ne change pas entre un débogage et une version Release.  
  
## <a name="remarks"></a>Notes  
 Le comportement de <xref:System.Diagnostics.Trace> est identique à celui de la classe Debug, mais dépend du symbole TRACE défini. Cela signifie que vous devez `#ifdef` tout code liées à la Trace pour éviter tout comportement de débogage dans une version Release.  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 L’exemple suivant exécute toujours les instructions de sortie, quelle que soit la compilation s’effectue avec **/DDEBUG** ou **/DTRACE**.  
  
### <a name="code"></a>Code  
  
```  
// mcpp_debug_class.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
   Trace::Unindent();  
  
   Debug::WriteLine("test");  
}  
```  
  
### <a name="output"></a>Sortie  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 Pour obtenir le comportement attendu (autrement dit, pas de sortie « test » imprimée pour une version release), vous devez utiliser le `#ifdef` et `#endif` directives. L’exemple de code précédent est modifié ci-dessous pour illustrer ce correctif :  
  
### <a name="code"></a>Code  
  
```  
// mcpp_debug_class2.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
  
#ifdef TRACE   // checks for a debug build  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
#endif  
   Trace::Unindent();  
  
#ifdef DEBUG   // checks for a debug build  
   Debug::WriteLine("test");  
#endif   //ends the conditional block  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)