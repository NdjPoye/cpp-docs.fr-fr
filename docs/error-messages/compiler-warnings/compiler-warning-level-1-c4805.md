---
title: Compilateur avertissement (niveau 1) C4805 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4805
dev_langs:
- C++
helpviewer_keywords:
- C4805
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
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
ms.openlocfilehash: bbe709ec83a19f6e1f2ac58059be564f9bee60a2
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4805"></a>Avertissement du compilateur (niveau 1) C4805
'operation' : mélange risqué de type 'type' et type 'type' dans l’opération  
  
 Cet avertissement est généré pour les opérations de comparaison entre [bool](../../cpp/bool-cpp.md) et [int](../../c-language/integer-types.md). L’exemple suivant génère l’erreur C4805 :  
  
```  
// C4805.cpp  
// compile with: /W1  
int main() {  
   int i = 1;  
   bool b = true;  
  
   if (i == b) {   // C4805, comparing bool and int variables  
   }  
}  
```
