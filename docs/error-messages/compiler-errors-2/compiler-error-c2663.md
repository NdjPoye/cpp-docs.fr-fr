---
title: "Erreur du compilateur C2663 | Microsoft Docs"
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
  - "C2663"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2663"
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2663
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : les surcharges de 'nombre' n'ont pas de conversion autorisée pour le pointeur 'this'  
  
 Le compilateur n'a pas pu convertir `this` en l'une des versions surchargées de la fonction membre.  
  
 Cette erreur peut être provoquée en appelant une fonction membre non `const` sur un objet `const`.  Résolutions possibles :  
  
1.  Supprimez `const` de la déclaration de l'objet.  
  
2.  Ajoutez `const` à l'une des surcharges de la fonction membre.  
  
 L'exemple suivant génère l'erreur C2663 :  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```