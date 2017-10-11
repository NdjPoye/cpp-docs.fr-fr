---
title: Avertissement du compilateur C4439 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4439
dev_langs:
- C++
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: eec228922a6f5796587243fe2d1f2c6cc1cf6b1c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4439"></a>Avertissement du compilateur C4439
'fonction' : définition de fonction avec un type managé dans la signature doit avoir une convention d’appel __clrcall  
  
 Le compilateur a remplacé implicitement une convention d’appel avec [__clrcall](../../cpp/clrcall.md). Pour résoudre cet avertissement, supprimez le `__cdecl` ou `__stdcall` convention d’appel.  
  
 C4439 est toujours émis en tant qu’erreur. Vous pouvez désactiver cet avertissement avec le `#pragma warning` ou **/wd**; consultez [avertissement](../../preprocessor/warning.md) ou [Wn, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, Wall, /wd, / nous, /wo, /WV., /Won (niveau d’avertissement)](../../build/reference/compiler-option-warning-level.md)pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4439.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```
