---
title: "Avertissement du compilateur (niveau 1) C4005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4005"
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : redéfinition de macro  
  
 La macro est définie à deux reprises.  Le compilateur a utilisé la seconde définition de macro.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Définition d'une macro dans la ligne de commande et dans le code à l'aide d'une directive `#define`.  
  
2.  Macros importées depuis des fichiers Include.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Supprimez une des définitions.  
  
2.  Utilisez une directive [\#undef](../../preprocessor/hash-undef-directive-c-cpp.md) avant la seconde définition.  
  
 L'exemple suivant génère l'erreur C4005 :  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```