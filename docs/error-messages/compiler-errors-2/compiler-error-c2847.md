---
title: Erreur du compilateur C2847 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8406ea786def9c3241a0ae1de8743d53e91f96cd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2847"></a>Erreur du compilateur C2847
impossible d'appliquer sizeof à un type managé ou WinRT 'classe'  
  
 Le [sizeof](../../cpp/sizeof-operator.md) opérateur Obtient la valeur d’un objet au moment de la compilation. La taille d'un type valeur, d'une interface ou d'une classe managée ou WinRT est dynamique et ne peut pas, par conséquent, être connue au moment de la compilation.  
  
 Par exemple, l'exemple suivant génère l'erreur C2847 :  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  

