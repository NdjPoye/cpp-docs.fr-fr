---
title: Erreur du compilateur C2473 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bbc3432383e39913ed3cd89b310b00706a26a589
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2473"></a>Erreur du compilateur C2473
'identifier' : similaire à une définition de fonction, mais aucune liste de paramètres n’existe.  
  
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
