---
title: "Avertissement du compilateur (niveau 1) C4393 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4393"
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 1) C4393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : const n'a aucun effet sur les données membres de type 'littéral' ; ignoré  
  
 Un membre de données [littéral](../../windows/literal-cpp-component-extensions.md) a également été spécifié comme const. Étant donné qu'un membre de données implique const, vous n'avez pas besoin d'ajouter const à la déclaration.  
  
 L'exemple suivant génère l'erreur C4393 :  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```