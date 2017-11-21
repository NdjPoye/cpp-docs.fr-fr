---
title: Compilateur avertissement (niveau 1) C4258 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4258
dev_langs: C++
helpviewer_keywords: C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8b987b1ad156106e4944443b778275b7643d116
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4258"></a>Avertissement du compilateur (niveau 1) C4258
'variable' : définition de la boucle for ignorée ; la définition de la portée englobante est utilisée »  
  
 Sous [/Ze](../../build/reference/za-ze-disable-language-extensions.md) et [/Zc : forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), les variables définies dans un [pour](../../cpp/for-statement-cpp.md) boucle sont hors de portée après la **pour** boucle se termine. Cet avertissement se produit si une variable portant le même nom que la variable de boucle, mais définie dans la boucle englobante, est réutilisée dans la portée contenant la **pour** boucle. Exemple :  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```