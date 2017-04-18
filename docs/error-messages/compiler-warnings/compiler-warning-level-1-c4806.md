---
title: Compilateur avertissement (niveau 1) C4806 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 021b0a5fd91df53e8fd1cb297c5d697f7135ff89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4806"></a>Avertissement du compilateur (niveau 1) C4806
'opération' : opération risquée : aucune valeur de type 'type' promue en type 'type' ne peut être égale à la constante donnée  
  
 Ce message fournit un avertissement contre le code tel que `b == 3`, où `b` est de type `bool`. Les règles de promotion entraînent la promotion de `bool` en `int`. Cela est légal, mais ne peut jamais être **true**. L’exemple suivant génère l’erreur C4806 :  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```
