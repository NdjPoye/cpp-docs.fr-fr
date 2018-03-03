---
title: Compilateur avertissement (niveau 1) C4269 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d276aa5744d457ee987334d65728b1835593ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4269"></a>Avertissement du compilateur (niveau 1) C4269
'identificateur' : les données automatiques 'const' initialisées avec le constructeur de valeur par défaut généré par le compilateur produisent des résultats incertains  
  
 A **const** instance automatique d’une classe non triviale est initialisée avec un constructeur par défaut de généré par le compilateur.  
  
## <a name="example"></a>Exemple  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Étant donné que cette instance de la classe est générée sur la pile, la valeur initiale de `m_data` peut être n’importe quoi. En outre, il est un **const** de l’instance, la valeur de `m_data` ne peut jamais être modifiée.