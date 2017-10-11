---
title: Avertissement du compilateur C4950 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6a922a0ee324afcf5f263abe2189e4071c5575c7
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4950"></a>Avertissement du compilateur C4950
'type_or_member' : marqué comme obsolète  
  
Un membre ou type a été marqué comme obsolète avec la <xref:System.ObsoleteAttribute> attribut.  
  
L’avertissement C4950 est toujours présenté comme une erreur. Vous pouvez désactiver cet avertissement à l’aide de la [avertissement](../../preprocessor/warning.md) directive pragma ou [/wd](../../build/reference/compiler-option-warning-level.md) option du compilateur.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C4950 :  
  
```cpp  
// C4950.cpp  
// compile with: /clr  
using namespace System;  
  
// Any reference to Func3 should generate an error with message  
[System::ObsoleteAttribute("Will be removed in next version", true)]  
Int32 Func3(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt3 = ::Func3(2, 2);   // C4950  
}  
```
