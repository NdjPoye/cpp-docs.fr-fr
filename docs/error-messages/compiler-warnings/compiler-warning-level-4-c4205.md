---
title: Compilateur avertissement (niveau 4) C4205 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd40764ea6a37acf11a43fb08ffad80e4c1bd8c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4205"></a>Avertissement du compilateur (niveau 4) C4205
extension non standard utilisée : déclaration de fonction statique dans la portée de la fonction  
  
 Avec les extensions Microsoft (/Ze), **statique** fonctions peuvent être déclarées à l’intérieur d’une autre fonction. La fonction reçoit une portée globale.  
  
## <a name="example"></a>Exemple  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 De telles initialisations sont non valides sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).