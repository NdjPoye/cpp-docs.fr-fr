---
title: "Erreur du compilateur C3861 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3861"
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : identificateur introuvable  
  
 Le compilateur n'a pas pu résoudre une référence à un identificateur, même à l'aide d'une recherche dépendante d'un argument.  
  
 Pour corriger cette erreur, vérifiez la casse et l'orthographe dans la déclaration de l'identificateur.  Vérifiez que les [opérateurs de résolution de portée](../../cpp/scope-resolution-operator.md) et les [directives using](../../misc/using-directive-cpp.md) de l'espace de noms sont utilisés correctement.  Si l'identificateur est déclaré dans un fichier d'en\-tête, vérifiez que l'en\-tête est inclus avant d'être référencé.  Vérifiez également que l'identificateur n'est pas exclu par les [directives de compilation conditionnelles](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3861.  
  
```  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## Exemple  
 Les classes d'exceptions dans la bibliothèque standard C\+\+ sont désormais dans l'espace de noms `std`.  
  
```  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```