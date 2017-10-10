---
title: Erreur du compilateur C2675 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c9c5815e7c57eb2469599a26c2cbc5202018f27e
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2675"></a>Erreur du compilateur C2675
l’opérateur unaire 'opérateur' : 'type' ne définit pas cet opérateur ou une conversion vers un type acceptable pour l’opérateur prédéfini  
  
 L’erreur C2675 peut également se produire lors de l’utilisation d’un opérateur unaire, et le type ne définit pas l’opérateur ou une conversion vers un type acceptable pour l’opérateur prédéfini. Pour utiliser l'opérateur, vous devez le surcharger pour le type spécifié ou définir une conversion vers un type pour lequel l'opérateur est défini.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2675.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```
