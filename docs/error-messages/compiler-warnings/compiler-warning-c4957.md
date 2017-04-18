---
title: Avertissement du compilateur C4957 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8eb7283942a8a89fc3322983c41c68082b6c5cee
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4957"></a>Avertissement du compilateur C4957
'cast' : le cast explicite de 'cast_from' en 'cast_to' n’est pas vérifiable  
  
 Un cast aura pour résultat une image non vérifiable.  
  
 Certains casts sont « safe » (par exemple, un `static_cast` qui déclenche des conversions définies par l’utilisateur et un `const_cast`). A [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) est garantie pour produire du code vérifiable.  
  
 Pour plus d’informations, consultez [Code pur et vérifiable (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Cet avertissement est émis comme une erreur et peut être désactivé avec le [avertissement](../../preprocessor/warning.md) pragma ou [/wd](../../build/reference/compiler-option-warning-level.md) option du compilateur.  
  
 L’exemple suivant génère l’erreur C4957 :  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```
