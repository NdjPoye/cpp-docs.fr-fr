---
title: "Erreur du compilateur C3465 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3465"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3465"
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3465
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pour pouvoir utiliser le type 'type', vous devez faire référence à l’assembly 'assembly'  
  
 Le transfert de type fonctionne pour une application cliente jusqu’à ce que vous recompiliez le client. Pour ce faire, vous avez besoin d’une référence pour chaque assembly contenant la définition d’un type utilisé dans votre application cliente.  
  
 Pour plus d'informations, consultez [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant génère un assembly qui contient le nouvel emplacement d’un type.  
  
```  
// C3465.cpp // compile with: /clr /LD public ref class R { public: ref class N {}; };  
```  
  
## Exemple  
 L’exemple suivant génère un assembly qui contenait auparavant la définition du type, mais qui contient désormais la syntaxe de transfert du type.  
  
```  
// C3465_b.cpp // compile with: /clr /LD #using "C3465.dll" [ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3465.  
  
```  
// C3465_c.cpp // compile with: /clr // C3465 expected #using "C3465_b.dll" // Uncomment the following line to resolve. // #using "C3465.dll" int main() { R^ r = gcnew R(); }  
```