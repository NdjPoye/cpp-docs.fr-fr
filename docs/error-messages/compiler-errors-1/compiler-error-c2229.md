---
title: "Erreur du compilateur C2229 | Microsoft Docs"
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
  - "C2229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2229"
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' type a un tableau de taille zéro non conforme  
  
 Un membre d'une structure ou d'un champ de bits contient un tableau de taille zéro qui n'est pas le dernier membre.  
  
 Comme un tableau de taille zéro ne peut pas être utilisé comme dernier membre de la structure, vous devez spécifier sa taille lorsque vous allouez la structure.  
  
 Si le tableau de taille zéro n'est pas le dernier membre de la structure, le compilateur ne peut pas calculer l'offset pour les champs restants.  
  
 L'exemple suivant génère l'erreur C2229 :  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```