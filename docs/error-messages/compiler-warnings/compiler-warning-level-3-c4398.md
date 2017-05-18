---
title: Avertissement (niveau 3) du compilateur C4398 | Documents Microsoft
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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 18270bb89bcc5d1855750c572a5b6fb9e51c2ba3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4398"></a>Avertissement du compilateur (niveau 3) C4398
'variable' : objet global par processus ne peut pas fonctionner correctement avec plusieurs appdomains ; envisagez d’utiliser __declspec(appdomain)  
  
 Une fonction virtuelle avec [__clrcall](../../cpp/clrcall.md) convention d’appel dans un type natif provoque la création d’une application vtable par domaine. Cette variable ne peut pas résoudre correctement lorsqu’il est utilisé dans plusieurs domaines d’application.  
  
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
