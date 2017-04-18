---
title: Compilateur avertissement (niveau 3) C4373 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
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
ms.openlocfilehash: 36d4491f8a621f1ee97de9682faf94a26a89fa70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4373"></a>Avertissement du compilateur (niveau 3) C4373
'%$S' : la fonction virtuelle se substitue à '%$pS', les versions précédentes n’ont pas été substituées lorsque les paramètres ne différaient que par les qualificateurs const/volatile  
  
 Votre application contienne une méthode dans une classe dérivée qui substitue une méthode virtuelle dans une classe de base, et les paramètres de la méthode de substitution diffèrent uniquement par un [const](../../cpp/const-cpp.md) ou [volatile](../../cpp/volatile-cpp.md) qualificateur à partir des paramètres de la méthode virtuelle. Cela signifie que le compilateur doit lier une référence de fonction à la méthode dans la classe de base ou dans la classe dérivée.  
  
 Versions du compilateur antérieures à [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] lient la fonction à la méthode dans la classe de base, puis émet un message d’avertissement. Les versions suivantes du compilateur ignorent le qualificateur `const` ou `volatile` , lient la fonction à la méthode dans la classe dérivée, puis émettent l’avertissement `C4373`. Ce dernier comportement est conforme à la norme C++.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant génère l’avertissement C4373.  
  
```  
// c4373.cpp  
// compile with: /c /W3  
#include <stdio.h>  
struct Base  
{  
    virtual void f(int i) {  
        printf("base\n");  
    }  
};  
struct Derived : Base  
{  
    void f(const int i) {  // C4373  
        printf("derived\n");  
    }  
};  
void main()  
{  
    Derived d;  
    Base* p = &d;  
    p->f(1);  
}  
```  
  
```Output  
derived  
```
