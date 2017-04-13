---
title: Erreur du compilateur C2473 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2473
dev_langs:
- C++
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 30fe7daae04948c01feaa403172ed55ee816ff2f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2473"></a>Erreur du compilateur C2473
'identifier' : similaire à une définition de fonction, mais aucune liste de paramètres n’existe.  
  
 Le compilateur a détecté un élément qui ressemble à une fonction, sans liste de paramètres.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2473.  
  
```  
// C2473.cpp  
// compile with: /clr /c  
class A {  
   int i {}   // C2473  
};  
  
class B {  
   int i() {}   // OK  
};  
```
