---
title: Erreur du compilateur C3672 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f01237ca5ac90ea3def4a6d2733ef8dd700bf738
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3672"></a>Erreur du compilateur C3672
l’expression pseudo-destructeur peut uniquement être utilisée dans le cadre d’un appel de fonction  
  
 Un destructeur a été appelé de façon incorrecte.  Pour plus d’informations, consultez [destructeurs](../../cpp/destructors-cpp.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3672.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```
