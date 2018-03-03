---
title: Compilateur avertissement (niveau 3) C4398 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5ce6355e50c1ea2594820388edc34c69ea0e899
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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