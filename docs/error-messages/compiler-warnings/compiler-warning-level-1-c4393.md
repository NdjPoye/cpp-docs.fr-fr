---
title: Compilateur avertissement (niveau 1) C4393 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4393
dev_langs: C++
helpviewer_keywords: C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 76c29081f2423464f235e7ff15b76b7bdcb35d3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4393"></a>Avertissement du compilateur (niveau 1) C4393
'var' : const n’a aucun effet sur une donnée membre littérale ; ignoré  
  
 A [littéral](../../windows/literal-cpp-component-extensions.md) membre de données a également été spécifié comme const.  Dans la mesure où une donnée membre littérale implique const, il est inutile ajouter const à la déclaration.  
  
 L’exemple suivant génère l’erreur C4393 :  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```