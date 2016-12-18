---
title: "true (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "true_cpp"
  - "true"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "true (mot clé) (C++)"
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# true (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
        bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## Notes  
 Ce mot clé est l'une des deux valeurs d'une variable de type [bool](../cpp/bool-cpp.md) ou d'une expression conditionnelle \(une expression conditionnelle est maintenant une véritable expression booléenne\).  Si `i` est de type `bool`, alors l'instruction `i = true;` assigne **true** à `i`.  
  
## Exemple  
  
```  
// bool_true.cpp  
#include <stdio.h>  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
  **1**  
**0**   
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)