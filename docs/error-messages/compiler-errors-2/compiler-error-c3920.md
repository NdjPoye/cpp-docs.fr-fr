---
title: "Erreur du compilateur C3920 | Microsoft Docs"
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
  - "C3920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3920"
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : impossible de définir un opérateur WinRT ou CLR postfixé d'incrémentation\/de décrémentation L'appel de l'opérateur WinRT ou CLR postfixé entraînera l'appel de l'opérateur WinRT ou CLR préfixé correspondant \(op\_Increment\/op\_Decrement\), mais avec la sémantique postfixée  
  
 Windows Runtime et le CLR ne prennent pas en charge l'opérateur suffixé et les opérateurs suffixés définis par l'utilisateur ne sont pas autorisés.  Vous pouvez définir un opérateur préfixé afin qu'il soit utilisé à la fois pour les opérations antérieures et postérieures à l'incrémentation.  
  
 L'exemple suivant génère l'erreur C3920 et montre comment la corriger :  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```