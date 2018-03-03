---
title: Compilateur avertissement (niveau 4) C4460 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4460
dev_langs:
- C++
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa925e8d0ef7779f21485cb154b9b9209ce2388e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4460"></a>Avertissement du compilateur (niveau 4) C4460
paramètre de l'opérateur WinRT ou CLR 'opérateur' passé par référence. L'opérateur WinRT ou CLR 'opérateur' a une sémantique différente de celle de l'opérateur C++ 'opérateur', voulez-vous effectuer un passage par valeur ?  
  
 Vous avez passé une valeur par référence à un opérateur CLR ou Windows Runtime défini par l'utilisateur. Si la valeur est modifiée dans la fonction, notez que la valeur de retour de la fonction sera attribuée à la valeur retournée après l'appel de fonction. En C++ standard, la valeur modifiée est reflétée après l'appel de fonction.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'avertissement C4460 et montre comment le corriger.  
  
```  
// C4460.cpp  
// compile with: /W4 /clr   
#include <stdio.h>  
  
public value struct V {  
   static V operator ++(V& me) {   // C4460  
   // try the following line instead  
   // static V operator ++(V me) {  
  
      printf_s(__FUNCSIG__ " called\n");  
      V tmp = me;  
      me.m_i++;  
      return tmp;  
   }  
   int m_i;  
};  
  
int main() {  
   V v;  
   v.m_i = 0;  
  
   printf_s("%d\n", v.m_i);   // Should print 0  
   v++;   // Translates to "v = V::operator ++(v)"  
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning  
}  
```