---
title: "Erreur du compilateur C2179 | Microsoft Docs"
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
  - "C2179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2179"
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : un argument d'attribut ne peut pas utiliser de paramètres de type  
  
 Un paramètre de type générique est résolu pendant l'exécution.  Toutefois, un paramètre d'attribut doit être résolu au moment de la compilation.  Par conséquent, vous ne pouvez pas vous utiliser de paramètre de type générique comme argument d'un attribut.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2179 :  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```