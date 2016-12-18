---
title: "Classe de d&#233;bogage (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework (C++), Debug (classe)"
  - "Debug (classe)"
  - "Trace (classe), Visual C++"
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe de d&#233;bogage (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'utilisation de <xref:System.Diagnostics.Debug> dans une application Visual C\+\+, le comportement ne change pas entre une version de débogage et une version release.  
  
## Remarques  
 Le comportement vis\-à\-vis de <xref:System.Diagnostics.Trace> est identique à celui vis\-à\-vis de la classe Debug, mais dépend du symbole TRACE défini.  Cela signifie que vous devez appliquer `#ifdef` au code lié à Trace pour éviter un comportement debug dans une version release.  
  
## Exemple  
  
### Description  
 L'exemple suivant exécute toujours les instructions de sortie, que vous effectuez une compilation avec **\/DDEBUG** ou **\/DTRACE**.  
  
### Code  
  
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
  
### Sortie  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## Exemple  
  
### Description  
 Pour obtenir le comportement attendu \(autrement dit, pas de sortie "test" imprimée pour une version release\), vous devez utiliser les directives `#ifdef` et `#endif`.  L'exemple de code précédent est modifié ci\-dessous pour illustrer ce correctif :  
  
### Code  
  
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
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)