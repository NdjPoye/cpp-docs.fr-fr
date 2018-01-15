---
title: Compilateur avertissement (niveau 4) C4295 | Documents Microsoft
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2018
---
# <a name="compiler-warning-level-4-c4295"></a>Avertissement du compilateur (niveau 4) C4295
  
> '*tableau*' : tableau est trop petit pour comporter un caractère null de fin  
  
Un tableau a été initialisé, mais le dernier caractère dans le tableau n’est pas une valeur null ; accès au tableau sous forme de chaîne peut produire des résultats inattendus.  
  
## <a name="example"></a>Exemple  
  
L’exemple suivant génère l’erreur C4295. Pour résoudre ce problème, vous pouvez déclarer la taille du tableau plus volumineux pour contenir une caractère null de fin de la chaîne de l’initialiseur, ou vous pouvez utiliser une liste d’initialiseurs de tableau pour rendre l’intention clair qu’il s’agit d’un tableau de `char`, pas une chaîne se terminant par null.  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
