---
title: Erreur du compilateur C3490 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6439b48dc752d2bed01371cae59b2d77db16f1f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3490"></a>Erreur du compilateur C3490
impossible de modifier 'var' car il est accessible via un objet const  
  
 Une expression lambda déclarée dans une méthode `const` ne peut pas modifier des données membres non mutables.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimez le modificateur `const` de votre déclaration de méthode.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3490, car il modifie la variable membre `_i` dans une méthode `const` :  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant corrige l’erreur C3490 en supprimant le modificateur `const` de la déclaration de méthode :  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)