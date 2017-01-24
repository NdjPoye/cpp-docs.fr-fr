---
title: "finally | Microsoft Docs"
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
  - "finally (mot clé) (C++)"
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# finally
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En plus des clauses `try` et `catch`, la gestion des exceptions CLR prend en charge une clause `finally`.  La sémantique est la même que celle du bloc `__finally` dans la gestion structurée des exceptions \(SEH\).  Un bloc `__finally` peut suivre un bloc `try` ou `catch`.  
  
## Notes  
 L'objectif du bloc `finally` est de nettoyer les ressources abandonnées après que l'exception soit rencontrée.  Notez que le bloc `finally` est toujours exécuté, même si aucune exception n'a été levée.  Le bloc `catch` n'est exécuté si une exception managée est levée dans le bloc associé à `try`.  
  
 `finally` est un mot clé contextuel ; consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md) pour plus d'informations.  
  
## Exemple  
 L'exemple de code suivant montre un bloc `finally` simple.  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
  **dans catch**  
**MyException**  
**In finally**   
## Voir aussi  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)