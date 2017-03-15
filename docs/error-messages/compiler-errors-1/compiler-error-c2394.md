---
title: "Compiler Error C2394 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2394"
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'op'" : opérateur CLR ou WinRT non valide.Au moins l'un des paramètres doit avoir les types suivants : 'T^', 'T^%', 'T^&', où T \= 'your\_type'  
  
 Un opérateur dans un type managé ou Windows Runtime ne disposait pas d'au moins un paramètre dont le type est le même que le type de la valeur de retour de l'opérateur.  
  
 L'exemple suivant génère l'erreur C2394 :  
  
```  
// C2394.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y^ operator -(int i, char c);   // C2394  
  
   // OK  
   static Y^ operator -(Y^ hY, char c);  
   // or  
   static Y^ operator -(int i, Y^& rhY);  
};  
```