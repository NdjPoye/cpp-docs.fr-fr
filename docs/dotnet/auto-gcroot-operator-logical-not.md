---
title: "auto_gcroot::operator! | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr.auto_gcroot.operator!"
  - "auto_gcroot.operator!"
  - "msclr::auto_gcroot::operator!"
  - "auto_gcroot::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::operator!"
ms.assetid: f9728be3-2e09-4c01-a594-43e0d59d40d3
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::operator!
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur pour l'utilisation de `auto_gcroot` dans une expression conditionnelle.  
  
## Syntaxe  
  
```  
bool operator!() const;  
```  
  
## Valeur de retour  
 `true` si l'objet encapsulé est invalide ; `false` sinon.  
  
## Exemple  
  
```  
// msl_auto_gcroot_operator_not.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s;  
   if ( s ) Console::WriteLine( "s is valid" );  
   if ( !s ) Console::WriteLine( "s is invalid" );  
   s = "something";  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
   s.reset();  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
}  
```  
  
  **s n'est pas valide.**  
**maintenant s est valide**  
**maintenant s n'est pas valide**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_gcroot.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::operator bool](../dotnet/auto-gcroot-operator-bool.md)