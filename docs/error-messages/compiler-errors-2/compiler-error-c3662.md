---
title: Erreur du compilateur C3662 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3662
dev_langs:
- C++
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9e5f9c48b9884939c6236075b3cf2227163ab8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3662"></a>Erreur du compilateur C3662
'membre' : spécificateur de substitution 'spécificateur' uniquement autorisé sur les fonctions membres de classes managées ou WinRT  
  
 Un spécificateur de substitution a été utilisé sur un membre de type natif, ce qui n'est pas autorisé.  
  
 Pour plus d’informations, consultez [substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'erreur C3662.  
  
```  
// C3662.cpp  
// compile with: /clr /c  
struct S {  
   virtual void f();  
};  
  
struct S1 : S {  
   virtual void f() new;   // C3662  
};  
  
ref struct T {  
   virtual void f();  
};  
  
ref struct T1 : T {  
   virtual void f() new;   // OK  
};  
```