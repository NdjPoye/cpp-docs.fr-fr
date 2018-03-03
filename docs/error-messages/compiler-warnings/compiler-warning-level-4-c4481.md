---
title: Compilateur avertissement (niveau 4) C4481 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52c296251e22adef2702aa9feba2b1fe2bc5122e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4481"></a>Avertissement du compilateur (niveau 4) C4481
extension non standard utilisée : spécificateur 'mot_clé' de substitution  
  
 Un mot clé a été utilisé qui n’est pas dans la norme C++, par exemple, un des spécificateurs de substitution qui fonctionne également sous/CLR.  Pour plus d'informations, consultez  
  
-   [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Spécificateurs de substitution](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4481.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```