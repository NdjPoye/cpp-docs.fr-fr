---
title: Erreur du compilateur C3034 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3034
dev_langs:
- C++
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65db8f94bbc6a37ded8a566e52acd7370037863a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3034"></a>Erreur du compilateur C3034
La directive OpenMP 'directive1' ne peut pas être directement imbriquée dans la directive 'directive2'  
  
 Certaines directives ne peuvent pas être imbriquées. Pour corriger cette erreur, vous pouvez fusionner les instructions des deux directives dans le bloc d'une directive ou construire des directives consécutives.  
  
 L’exemple suivant génère l’erreur C3034 :  
  
```  
// C3034.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
  
   #pragma omp single  
   {  
      #pragma omp single   // C3034   
      {  
      ;  
      }  
   }  
  
   // Two consecutive single clauses are OK.  
   #pragma omp single  
   {  
   }  
  
   #pragma omp single  
   {  
   }  
}  
```
