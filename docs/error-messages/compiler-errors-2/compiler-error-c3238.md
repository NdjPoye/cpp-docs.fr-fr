---
title: "Erreur du compilateur C3238 | Microsoft Docs"
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
  - "C3238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3238"
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : un type portant ce nom a déjà été transféré à l’assembly 'assembly'  
  
 Un type a été défini dans une application cliente qui est aussi définie, via la syntaxe de transfert de type, dans un assembly référencé. Les deux types ne peuvent pas être définis dans l’étendue de l’application.  
  
 Pour plus d'informations, voir [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Exemple  
 L’exemple suivant crée un assembly qui contient un type qui a été transféré à partir d’un autre assembly.  
  
```  
// C3238.cpp // compile with: /clr /LD public ref class R {};  
```  
  
## Exemple  
 L’exemple suivant crée un assembly qui contenait la définition du type, mais qui ne contient maintenant que la syntaxe de transfert de type.  
  
```  
// C3238_b.cpp // compile with: /clr /LD #using "C3238.dll" [ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3238 :  
  
```  
// C3238_c.cpp // compile with: /clr /c // C3238 expected // Delete the following line to resolve. #using "C3238_b.dll" public ref class R {};  
```