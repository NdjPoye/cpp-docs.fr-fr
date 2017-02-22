---
title: "Erreur du compilateur C2010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2010"
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'caractère' : inattendu dans la liste de paramètres formels d'une macro  
  
 Caractère incorrectement utilisé dans la liste de paramètres formels d'une définition de macro.  Supprimez le caractère pour corriger l'erreur.  
  
 L'exemple suivant génère l'erreur C2010 :  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```