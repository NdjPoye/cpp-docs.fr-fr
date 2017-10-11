---
title: Erreur du compilateur C3174 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3174
dev_langs:
- C++
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2dea7e564b7685cf58f9d97f15659d7f911817a6
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3174"></a>Erreur du compilateur C3174
attribut de module n’a pas été spécifié.  
  
 Un programme qui utilise des attributs Visual C++ ne pas également utiliser le [module](../../windows/module-cpp.md) attribut, qui est requis dans tout programme qui utilise des attributs.  
  
 L’exemple suivant génère l’erreur C3174 :  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```
