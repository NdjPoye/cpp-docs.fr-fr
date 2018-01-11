---
title: Compilateur avertissement (niveau 1) C4572 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4572
dev_langs: C++
helpviewer_keywords: C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee599d1385d71fee1b03d4298f27e1c8ed5ccbd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4572"></a>Avertissement du compilateur (niveau 1) C4572
L’attribut [ParamArray] est déconseillé sous/CLR, utilisez '...' à la place  
  
 Un style obsolète de spécification d’une liste d’arguments variable a été utilisé. Lors de la compilation pour le CLR, utilisez la syntaxe des points de suspension à la place de <xref:System.ParamArrayAttribute>. Pour plus d’informations, consultez [listes d’arguments variables (...) (C + C++ / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4572.  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```