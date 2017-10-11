---
title: Erreur du compilateur C3842 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d9fe94a50939af6d28f9dc29eb1eb7aa91a7d47c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3842"></a>Erreur du compilateur C3842
'fonction' : les qualificateurs 'const' et 'volatile' ne sont pas pris en charge pour les fonctions membres des types WinRT ou managés  
  
 [const](../../cpp/const-cpp.md) et [volatile](../../cpp/volatile-cpp.md) ne sont pas pris en charge sur les fonctions membres de types managés ou Windows Runtime.  
  
 L'exemple suivant génère l'erreur C3842 :  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
```
