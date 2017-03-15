---
title: "Compiler Error C2395 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2395"
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'op'' : opérateur CLR ou WinRT non valide.Au moins l'un des paramètres doit avoir les types suivants : 'T', 'T%', 'T&', 'T^', 'T^%', 'T^&', où T \= 'your\_type'  
  
 Un opérateur dans un type managé ou Windows Runtime ne disposait pas d'au moins un paramètre dont le type est le même que le type de la valeur de retour de l'opérateur.  
  
 L'exemple suivant génère l'erreur C2395 et montre comment la corriger :  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```