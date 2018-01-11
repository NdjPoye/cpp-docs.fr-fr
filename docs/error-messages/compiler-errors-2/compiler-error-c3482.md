---
title: Erreur du compilateur C3482 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3482
dev_langs: C++
helpviewer_keywords: C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ff7a17d663be7168c5743838d782043d7c0ee92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3482"></a>Erreur du compilateur C3482
'this' peut uniquement être utilisé en tant que capture lambda dans une fonction membre non statique  
  
 Vous ne pouvez pas passer `this` à la liste de capture d’une expression lambda qui est déclarée dans une méthode statique ou une fonction globale.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Convertissez la fonction englobante en méthode non statique.  
  
-   Vous pouvez aussi supprimer le pointeur `this` de la liste de capture de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3482 :  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)