---
title: "auto_handle::operator (bool) | Microsoft Docs"
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
  - "auto_handle.operator bool"
  - "msclr.auto_handle.operator bool"
  - "operator bool"
  - "msclr::auto_handle::operator bool"
  - "auto_handle::operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::operator (bool)"
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::operator (bool)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur pour l'utilisation de `auto_handle` dans une expression conditionnelle.  
  
## Syntaxe  
  
```  
operator bool();  
```  
  
## Valeur de retour  
 `true` si l'objet wrappé est valide; sinon `false`.  
  
## Notes  
 L'opérateur convertit en fait à `_detail_class::_safe_bool` qui est plus sûr que `bool` car il ne peut pas être converti en un type intégral.  
  
## Exemple  
  
```  
// msl_auto_handle_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1;  
   auto_handle<String> s2 = "hi";  
   if ( s1 ) Console::WriteLine( "s1 is valid" );  
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );  
   if ( s2 ) Console::WriteLine( "s2 is valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );  
   s2.reset();  
   if ( s2 ) Console::WriteLine( "s2 is now valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );  
}  
```  
  
  **s1 n'est pas valide.**  
**s2 est valide**  
**s2 est désormais non valide**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_handle.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_handle, membres](../dotnet/auto-handle-members.md)   
 [auto\_handle::operator\!](../dotnet/auto-handle-operator-logical-not.md)