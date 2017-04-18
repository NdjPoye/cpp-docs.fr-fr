---
title: Erreur du compilateur C2474 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: 3
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
ms.openlocfilehash: 6ac71627aa3f87d3e61cc2815a70eee4884c0bd3
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2474"></a>Erreur du compilateur C2474
'keyword' : point-virgule adjacent manquant ; il peut s’agir d’un mot clé ou d’un identificateur.  
  
 Le compilateur attendait un point-virgule et n’a pas pu identifier ce que vous souhaitiez faire. Ajoutez le point-virgule pour résoudre cette erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2474.  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```
