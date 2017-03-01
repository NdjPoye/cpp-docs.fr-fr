---
title: Erreur du compilateur C3063 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: ce6a597e0246cee5c62dd6612d48fe4946505e77
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3063"></a>Erreur du compilateur C3063
l’opérateur 'opérateur' : tous les opérandes doivent avoir le même type énumération  
  
Lorsque vous utilisez des opérateurs sur les énumérateurs, les deux opérandes doivent être du type énumération. Pour plus d’informations, consultez [Comment : définir et consommer des énumérateurs dans c++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C3063 et montre comment résoudre le problème :  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```
