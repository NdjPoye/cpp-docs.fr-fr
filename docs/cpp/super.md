---
title: __super | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __super_cpp
- __super
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
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
ms.openlocfilehash: 64600f8cf642b0c7906873a73aa4da41897a57f5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="super"></a>__super
**Section spécifique à Microsoft**  
  
 Permet de déclarer explicitement que vous appelez une implémentation de classe de base pour une fonction que vous substituez.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>Remarques  
 Toutes les méthodes de classe de base accessibles sont considérées pendant la phase de résolution de surcharge, et la fonction qui fournit la meilleure correspondance est celle qui est appelée.  
  
 `__super` peut apparaître uniquement dans le corps d'une fonction membre.  
  
 `__super` ne peut pas être utilisé avec une déclaration using. Consultez [à l’aide de la déclaration](../cpp/using-declaration.md) pour plus d’informations.  
  
 Avec l’introduction de [attributs](../windows/cpp-attributes-reference.md) qui injectent du code, votre code peut contenir un ou plusieurs classes de base dont vous savez ne peut-être pas, mais que les noms contiennent des méthodes que vous souhaitez appeler.  
  
## <a name="example"></a>Exemple  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)
