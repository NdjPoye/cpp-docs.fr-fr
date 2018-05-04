---
title: __super | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ce48232884d1ab242ed52f82f614de058a2f91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
  
## <a name="remarks"></a>Notes  
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