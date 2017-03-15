---
title: "Erreur du compilateur C3541 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3541"
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« type » : typeid ne peut pas s'appliquer à un type qui contient « auto »  
  
 L'opérateur [typeid](../../windows/typeid-cpp-component-extensions.md) ne peut pas être appliqué au type indiqué car il contient le spécificateur `auto`.  
  
## Exemple  
 L'exemple suivant donne C3541.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(déduire le type de variable\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../../windows/typeid-cpp-component-extensions.md)