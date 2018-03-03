---
title: Compilateur avertissement (niveau 1) C4715 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4715
dev_langs:
- C++
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b060585cd3ba6b51c9c91d42e5f3fecaf74ae1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4715"></a>Avertissement du compilateur (niveau 1) C4715
'fonction' : une valeur de retour pas tous les chemins d’accès de contrôle  
  
 La fonction spécifiée ne peut potentiellement pas retourner une valeur.  
  
## <a name="example"></a>Exemple  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Pour éviter cet avertissement, modifiez le code afin que tous les chemins d’affectent une valeur de retour à la fonction :  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Il est possible que votre code peut contenir un appel à une fonction qui ne retourne jamais, comme dans l’exemple suivant :  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Ce code génère également un avertissement, car le compilateur ne sait pas que `fatal` ne retourne jamais. Pour éviter que ce code génère un message d’erreur, déclarez `fatal` à l’aide de [__declspec (noreturn)](../../cpp/noreturn.md).