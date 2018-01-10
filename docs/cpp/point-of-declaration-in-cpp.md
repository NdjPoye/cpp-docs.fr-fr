---
title: "Point de déclaration en C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64c1fa1d6d8feb4b869957101bb4b37f125d0f8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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