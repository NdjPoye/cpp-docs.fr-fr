---
title: "Erreur du compilateur C2561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2561"
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : la fonction doit retourner une valeur  
  
 La fonction a été déclarée comme retournant une valeur, mais sa définition ne contient pas d'instruction `return`.  
  
 Cette erreur peut être provoquée par un prototype de fonction incorrect :  
  
1.  Si la fonction ne retourne pas de valeur, déclarez\-la avec le type de retour [void](../../cpp/void-cpp.md).  
  
2.  Vérifiez que toutes les branches possibles de la fonction retournent une valeur du type déclaré dans le prototype.  
  
3.  Les fonctions C\+\+ contenant des routines d'assembly inline qui stockent la valeur de retour dans le registre `AX` peuvent demander une instruction return.  Copiez la valeur de `AX` dans une variable temporaire et retournez cette variable à partir de la fonction.  
  
 L'exemple suivant génère l'erreur C2561 :  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```