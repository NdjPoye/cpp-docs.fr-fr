---
title: Compilateur avertissement (niveau 4) C4918 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4918
dev_langs:
- C++
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
caps.latest.revision: 7
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
ms.openlocfilehash: ec8c01dc780b8f7ad5d3f10cfd8dea890fb64f70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4918"></a>Avertissement du compilateur (niveau 4) C4918
'character' : caractère non valide dans la liste d’optimisation pragma  
  
 Un caractère inconnu a été trouvé dans la liste d’optimisation d’une [optimiser](../../preprocessor/optimize.md) instruction pragma.  
  
 Par exemple, l’instruction suivante génère l’avertissement C4918 :  
  
```  
// C4918.cpp  
// compile with: /W4  
#pragma optimize("X", on) // C4918 expected  
int main()  
{  
}  
```
