---
title: Erreur du compilateur C3861 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 177890dcd3ff2abf07f5d9e282efd4a9fd7121a7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3861"></a>Erreur du compilateur C3861
'identificateur' : identificateur introuvable  
  
Le compilateur n’a pas pu résoudre une référence à un identificateur, même à l’aide d’une recherche dépendante d’un argument.  
  
Pour corriger cette erreur, vérifiez la casse et l'orthographe dans la déclaration de l'identificateur. Vérifiez que [opérateurs de résolution de portée](../../cpp/scope-resolution-operator.md) et espace de noms [à l’aide de directives](../../cpp/namespaces-cpp.md#using_directives) sont utilisés correctement. Si l'identificateur est déclaré dans un fichier d'en-tête, vérifiez que l'en-tête est inclus avant d'être référencé. Vérifiez également que l’identificateur n’est pas exclu par [directives de compilation conditionnelle](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
## <a name="example"></a>Exemple  
L'exemple suivant génère l'erreur C3861.  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Exemple  
Les classes d'exceptions dans la bibliothèque standard C++ sont désormais dans l'espace de noms `std`.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```
