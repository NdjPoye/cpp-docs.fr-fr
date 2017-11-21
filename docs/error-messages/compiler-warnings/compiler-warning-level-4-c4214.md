---
title: Compilateur avertissement (niveau 4) C4214 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4214
dev_langs: C++
helpviewer_keywords: C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 14d7a13d87d665cb39dbb40603ce6a01a9b8d5a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4214"></a>Avertissement du compilateur (niveau 4) C4214
extension non standard utilisée : les types autres qu’int de champ de bits  
  
 Avec les extensions Microsoft (/Ze), les membres de structure de champ de bits peuvent être de n’importe quel type entier.  
  
## <a name="example"></a>Exemple  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 Ces champs de bits sont non valides sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).