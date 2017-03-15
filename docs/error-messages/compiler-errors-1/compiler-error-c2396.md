---
title: "Compiler Error C2396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2396"
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'type'' : la fonction de conversion CLR ou WinRT définie par l'utilisateur n'est pas valide.La conversion doit être opérée depuis ou vers : 'T^', 'T^%', 'T^&', où T \= 'your\_type'  
  
 Une fonction de conversion dans un type managé ou Windows Runtime ne disposait pas d'au moins un paramètre dont le type est le même que le type qui contient la fonction de conversion.  
  
 L'exemple suivant génère l'erreur C2396 et montre comment la corriger :  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```