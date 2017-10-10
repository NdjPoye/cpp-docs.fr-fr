---
title: Erreur du compilateur C2513 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7eb4e7c63821f449bf9677cb5fe03c448bbbc6ee
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2513"></a>Erreur du compilateur C2513
'type' : aucune variable déclarée avant '='  
  
 Le spécificateur de type apparaît dans la déclaration sans identificateur de variable.  
  
 L’exemple suivant génère l’erreur C2513 :  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Cette erreur peut également être générée à la suite d’un travail de mise en conformité du compilateur pour Visual Studio .NET 2003 : initialisation d’un typedef ne sont plus autorisé. L’initialisation d’un typedef n’est pas autorisée par la norme et génère une erreur du compilateur.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Une alternative consisterait à supprimer `typedef` pour définir une variable avec la liste d’initialiseurs d’agrégat, mais cela n’est pas recommandée car elle créer une variable avec le même nom que le type et masquer le nom de type.
