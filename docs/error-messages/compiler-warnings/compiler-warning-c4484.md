---
title: Avertissement du compilateur C4484 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa5f209dd3a77bcc4ec3c21d589fb8ba1ed3faf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4484"></a>Avertissement du compilateur C4484
'fonction_substitution' : correspond à la méthode de classe ref de base 'fonction_classe_base', mais n’est pas marqué comme 'virtual', 'new' ou 'override' ; 'new' (et non 'virtual') sont supposé.  
  
 Lors de la compilation avec **/CLR**, le compilateur ne substitue pas implicitement une fonction de classe de base, ce qui signifie que la fonction aura un nouvel emplacement dans vtable. Pour résoudre, spécifiez explicitement si une fonction est un remplacement.  
  
 Pour plus d'informations, voir :  
  
-   [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [New (nouvel emplacement dans vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 est toujours émis en tant qu’erreur. Utilisez le [avertissement](../../preprocessor/warning.md) pragma pour supprimer l’erreur C4484.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4484.  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```