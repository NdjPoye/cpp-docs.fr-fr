---
title: Erreur du compilateur C3768 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: cb9c1c3a41deb35e6aa82d3d77e61dfd4b15a7cb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3768"></a>Erreur du compilateur C3768
impossible d'accepter l'adresse d'une fonction vararg virtuelle dans du code managé pur  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Lors de la compilation avec `/clr:pure`, vous ne pouvez pas prendre l’adresse d’un ordinateur virtuel, `vararg` (fonction).  
  
## <a name="example"></a>Exemple  

 L’exemple suivant génère C3768 :  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```
