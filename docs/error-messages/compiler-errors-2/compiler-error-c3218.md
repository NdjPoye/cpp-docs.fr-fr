---
title: "Erreur du compilateur C3218 | Microsoft Docs"
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
  - "C3218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3218"
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : type non autorisé comme contrainte  
  
 Pour qu'un type soit une contrainte, il doit être un type valeur ou une référence à une classe ou interface managées.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3218 :  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```