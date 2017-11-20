---
title: "Du compilateur (niveau 1) d’avertissement C4091 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4091
dev_langs: C++
helpviewer_keywords: C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9b40596872bba7cc914f148f36c7d31dde5dd103
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4091"></a>Du compilateur (niveau 1) d’avertissement C4091
'keyword' : ignoré à gauche de 'type' quand aucune variable est déclarée.  
  
 Le compilateur a détecté une situation dans laquelle l’utilisateur attendait probablement une variable qui doit être déclarée, mais le compilateur n’a pas la possibilité de déclarer la variable.  
  
## <a name="example"></a>Exemple  
 A `__declspec` attribut au début d’une déclaration de type défini par l’utilisateur s’applique à la variable de ce type. C4091 indique qu’aucune variable est déclarée. L’exemple suivant génère C4091.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>Exemple  
 Si un identificateur est un typedef, il ne peut pas être également un nom de variable. L’exemple suivant génère C4091.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```