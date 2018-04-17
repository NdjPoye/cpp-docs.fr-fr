---
title: Erreur du compilateur C3851 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 792d13ece8b864b3d8d7e251bf530f685a02ccf7
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="compiler-error-c3851"></a>Erreur du compilateur C3851
« char » : un nom de caractère universel ne peut pas désigner un caractère du jeu de caractères de base  
  
 Dans le code compilé en C++, vous ne pouvez pas utiliser un nom de caractère universel représentant un caractère dans le jeu de caractères source de base en dehors d’une chaîne ou d’un littéral de caractère. Pour plus d’informations, consultez [jeux de caractères](../../cpp/character-sets.md). Dans le code compilé en tant que C, vous ne pouvez pas utiliser un nom de caractère universel pour les caractères dans la plage 0x20-0x7f, inclusivement, excepté pour 0x24 (« $ »), 0x40 (« @ ») ou 0x60 (« ` »).  
  
 Les exemples suivants génèrent C3851 et montrent comment résoudre le problème :  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```