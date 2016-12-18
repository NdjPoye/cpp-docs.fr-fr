---
title: "Erreur du compilateur C3195 | Microsoft Docs"
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
  - "C3195"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3195"
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3195
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : est réservé et ne peut pas être utilisé comme membre d'une classe ref ou d'un type valeur.Les opérateurs CLR ou WinRT doivent être définis à l'aide du mot clé 'operator'  
  
 Le compilateur a détecté une définition d'opérateur utilisant la syntaxe des extensions managées pour C\+\+.  
  
 Utilisez la nouvelle syntaxe C\+\+ ou l'option de compilateur **\/clr:oldSyntax** pour activer la syntaxe des extensions managées pour C\+\+.  
  
 L'exemple suivant génère l'erreur C3195 et montre comment la corriger :  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```