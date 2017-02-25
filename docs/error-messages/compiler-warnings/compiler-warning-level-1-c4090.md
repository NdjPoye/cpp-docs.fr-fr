---
title: "Avertissement du compilateur (niveau 1) C4090 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4090"
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opération' : qualificateurs 'modificateurs' différents  
  
 Une variable utilisée dans une opération est définie avec un modificateur spécifié qui l'empêche d'être modifiée sans détection par le compilateur.  L'expression est compilée sans modification.  
  
 Cet avertissement peut être provoqué lorsqu'un pointeur vers un élément **const** ou `volatile` est assigné à un pointeur non déclaré comme pointant vers **const** ou `volatile`.  
  
 Cet avertissement apparaît pour les programmes C.  Dans un programme C\+\+, le compilateur génère une erreur : [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).  
  
 L'exemple suivant génère l'erreur C4090 :  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```