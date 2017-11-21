---
title: Erreur du compilateur C2556 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2556
dev_langs: C++
helpviewer_keywords: C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6678c34022c28dccfa5920809e7b8d6db0d39546
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2556"></a>Erreur du compilateur C2556
'identificateur' : les fonctions surchargées ne diffèrent que par le type de retour  
  
 Les fonctions surchargées ont des types de retour différents mais la même liste de paramètres. Chaque fonction surchargée doit avoir une liste de paramètres formels distincte.  
  
 L’exemple suivant génère l’erreur C2556 :  
  
```  
// C2556.cpp  
// compile with: /c  
class C {  
   int func();  
   double func();   // C2556  
   int func(int i);   // ok parameter lists differ  
};  
```