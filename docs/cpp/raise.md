---
title: __raise | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs:
- C++
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0303198f352b97cf84a97d63dce18055e63622b1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="raise"></a>__raise
Met en évidence le site d'appel d'un événement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## <a name="remarks"></a>Remarques  
 À partir du code managé, un événement ne peut être déclenché que par la classe dans laquelle il est défini. Consultez [événement](../windows/event-cpp-component-extensions.md) pour plus d’informations.  
  
 Le mot clé `__raise` entraîne l'émission d'une erreur si vous appelez un non-événement.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## <a name="example"></a>Exemple  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Gestion des événements](../cpp/event-handling.md)   
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)
