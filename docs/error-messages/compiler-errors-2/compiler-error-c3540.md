---
title: "Erreur du compilateur C3540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3540"
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« type » : sizeof ne peut pas s'appliquer à un type qui contient « auto »  
  
 L'opérateur [sizeof](../../cpp/sizeof-operator.md) ne peut pas être appliqué au type indiqué car il contient le spécificateur `auto`.  
  
## Exemple  
 L'exemple suivant donne C3540.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(déduire le type de variable\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof, opérateur](../../cpp/sizeof-operator.md)