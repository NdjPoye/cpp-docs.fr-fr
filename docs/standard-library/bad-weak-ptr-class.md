---
title: bad_weak_ptr, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::bad_weak_ptr
dev_langs:
- C++
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 940a497217ffb4788adb24f1a4a67ce3eb04bc12
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="badweakptr-class"></a>bad_weak_ptr, classe
Signale une exception weak_ptr incorrecte.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class bad_weak_ptr : public std::exception 
 {  
public:  
    bad_weak_ptr();
    const char *what() throw();
 };  
```  
  
## <a name="remarks"></a>Notes  
 La classe décrit une exception qui peut être levée à partir du constructeur de [classe shared_ptr](../standard-library/shared-ptr-class.md) qui accepte un argument de type [classe weak_ptr](../standard-library/weak-ptr-class.md). La fonction membre `what` retourne `"bad_weak_ptr"`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
 
int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```  
  
```Output  
bad weak pointer  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [weak_ptr, classe](../standard-library/weak-ptr-class.md)

