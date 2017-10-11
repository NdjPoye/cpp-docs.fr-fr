---
title: Erreur du compilateur C3809 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e68e6f3b1309a0135b439bfe8f3f067a0c90a6ac
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3809"></a>Erreur du compilateur C3809
'classe' : un type managé ou WinRT ne peut pas avoir de fonctions/classes/interfaces friend  
  
 Les types managés et les types Windows Runtime n'autorisent pas l'utilisation des friends. Pour corriger cette erreur, ne déclarez ne pas de friend à l'intérieur des types managés ou Windows Runtime.  
  
 L'exemple suivant génère l'erreur C3809 :  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```
