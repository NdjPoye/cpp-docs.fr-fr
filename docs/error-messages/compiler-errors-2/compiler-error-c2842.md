---
title: "Erreur du compilateur C2842 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2842"
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : un type managé ou WinRT ne peut pas définir son propre 'operator new' ou 'operator delete'  
  
 Vous pouvez définir votre propre [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) ou [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) pour gérer l'allocation de mémoire sur le tas natif.  Toutefois, les classes de référence ne peuvent pas définir ces opérateurs car ils sont alloués seulement sur le tas managé.  
  
 Pour plus d'informations, consultez [Opérateurs définis par l'utilisateur](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2842.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C2842.  
  
```  
// C2842_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```