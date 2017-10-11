---
title: Erreur du compilateur C2360 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2360
dev_langs:
- C++
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 12b62d31c125dfc353623fa7cf10fce578698332
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2360"></a>Erreur du compilateur C2360
l’initialisation de 'identificateur' est ignorée par l’étiquette 'case'  
  
 L’initialisation de `identifier` peut être ignorée dans un `switch` instruction. Vous ne peut pas sauter au-delà d’une déclaration avec un initialiseur, sauf si la déclaration est englobée dans un bloc. (Sauf si elle est déclarée dans un bloc, la variable est dans la portée jusqu'à la fin de la `switch` instruction.)  
  
 L’exemple suivant génère l’erreur C2360 :  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 Résolution possible :  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```
