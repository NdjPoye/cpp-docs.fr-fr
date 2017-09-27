---
title: "Point de déclaration en C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
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
ms.openlocfilehash: 77f66182052cc2a031b7f1f8db8018f49b36801d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="point-of-declaration-in-c"></a>Point de déclaration en C++
Un nom est considéré comme déclaré immédiatement après son déclarateur mais avant son initialiseur (facultatif). (Pour plus d’informations sur les déclarateurs, consultez [déclarations et définitions](declarations-and-definitions-cpp.md).)  
  
 Considérez cet exemple :  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Si le point de déclaration ont été *après* l’initialisation, puis local `dVar` serait initialisée à 7,0, la valeur de la variable globale `dVar`. Toutefois, comme ce n'est pas le cas, `dVar` est initialisé avec une valeur non définie.  
  
## <a name="see-also"></a>Voir aussi  
 [Portée](../cpp/scope-visual-cpp.md)
