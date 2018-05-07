---
title: Compilateur avertissement (niveau 3) C4398 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ace2df75b5d2579b66a4d3930470021726ba4c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4398"></a>Avertissement du compilateur (niveau 3) C4398
'variable' : objet global par processus ne peut pas fonctionner correctement avec plusieurs appdomains ; envisagez d’utiliser __declspec(appdomain)  
  
 Une fonction virtuelle avec [__clrcall](../../cpp/clrcall.md) convention d’appel dans un type natif provoque la création d’une application vtable par domaine. Une variable de ce type ne peut pas résoudre correctement lorsqu’il est utilisé dans plusieurs domaines d’application.  
  
 Vous pouvez résoudre cet avertissement en marquant explicitement la variable `__declspec(appdomain)`. Dans les versions de Visual Studio antérieures à Visual Studio 2017, vous pouvez résoudre cet avertissement en compilant avec **/CLR : pure**, ce qui rend les variables globales par appdomain par défaut.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [domaines d’Application et Visual C++](../../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4398.  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```