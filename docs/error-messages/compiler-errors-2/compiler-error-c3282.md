---
title: "Compiler Error C3282 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3282"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3282"
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compiler Error C3282
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les listes de paramètres génériques ne peuvent apparaître que sur les classes, structures ou fonctions managées ou WinRT  
  
 Une liste de paramètres génériques a été utilisée de façon incorrecte.  Pour plus d'informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3282 et montre comment la corriger.  
  
```  
// C3282.cpp  
// compile with: /clr /c  
generic <typename T> int x;   // C3282  
  
ref struct GC0 {  
   generic <typename T> int x;   // C3282  
};  
  
// OK  
generic <typename T>  
ref class M {};  
```