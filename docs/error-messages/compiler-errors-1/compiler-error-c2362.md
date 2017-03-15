---
title: "Erreur du compilateur C2362 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2362"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2362"
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2362
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'initialisation de 'identificateur' est ignorée par l''étiquette goto'  
  
 Lors de la compilation à l'aide de [\/Za](../../build/reference/za-ze-disable-language-extensions.md), l'accès à l'étiquette empêche l'initialisation de l'identificateur.  
  
 Vous ne pouvez pas aller au\-delà d'une déclaration avec un initialiseur sauf si la déclaration figure dans un bloc qui n'est pas entré ou si la variable a déjà été initialisée.  
  
 L'exemple suivant génère l'erreur C2326 :  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 Résolution possible :  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```