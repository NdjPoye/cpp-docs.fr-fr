---
title: Erreur du compilateur C3535 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3535
dev_langs:
- C++
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff9935f4a46ba2c3a268ebb761153948ccd82f47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3535"></a>Erreur du compilateur C3535
Impossible de déduire le type de 'type1' à partir de 'type2'  
  
 Le type de la variable déclarée par le `auto` mot clé ne peut pas être déduit du type de l’expression d’initialisation. Par exemple, cette erreur se produit si l’expression d’initialisation a la valeur `void`, qui n’est pas un type.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Assurez-vous que le type de l’expression d’initialisation n’est pas `void`.  
  
2.  Assurez-vous que la déclaration n’est pas un pointeur vers un type fondamental. Pour plus d’informations, consultez [Types fondamentaux](../../cpp/fundamental-types-cpp.md).  
  
3.  Assurez-vous que si la déclaration est un pointeur vers un type, l’expression d’initialisation est un type pointeur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3535 parce que l’expression d’initialisation prend la valeur `void`.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3535 parce que l’instruction déclare la variable `x` comme un pointeur vers un type déduit, mais le type de l’initialiseur de l’expression est double. Par conséquent, le compilateur ne peut pas déduire le type de la variable.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3535 parce que variable `p` déclare un pointeur vers un type déduit, mais l’expression d’initialisation n’est pas un type pointeur.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [Types fondamentaux](../../cpp/fundamental-types-cpp.md)