---
title: Erreur du compilateur C3530 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0d66e76fc3e44a037f52aa6e217fae848f1338d2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3530"></a>Erreur du compilateur C3530
'auto' ne peut pas être combiné avec n’importe quel autre spécificateur de type  
  
 Un spécificateur de type est utilisé avec le `auto` (mot clé).  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  N’utilisez pas un spécificateur de type dans une déclaration de variable qui utilise le `auto` (mot clé).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3530 parce que variable `x` est déclaré avec le `auto` (mot clé) et le type `int`, et parce que l’exemple est compilé avec **/Zc : auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)
