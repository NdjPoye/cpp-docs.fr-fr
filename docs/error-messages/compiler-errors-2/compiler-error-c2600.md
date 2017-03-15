---
title: "Erreur du compilateur C2600 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2600"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2600"
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2600
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : impossible de définir une fonction membre spéciale générée par le compilateur \(doit être déclarée d'abord dans la classe\)  
  
 Pour que les fonctions membres telles que les constructeurs ou les destructeurs puissent être définies pour une classe, elles doivent être déclarées dans la classe.  Le compilateur peut générer des constructeurs et des destructeurs par défaut \(appelés fonctions membres spéciales\) si aucun n'est déclaré dans la classe.  Cependant, si vous définissez une de ces fonctions sans déclaration correspondante dans la classe, le compilateur détecte un conflit.  
  
 Pour corriger cette erreur, dans la déclaration de la classe, déclarez chaque fonction membre que vous définissez en dehors de la déclaration de la classe.  
  
 L'exemple suivant génère l'erreur C2600 :  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```