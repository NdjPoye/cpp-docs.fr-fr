---
title: Erreur du compilateur C2689 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2689
dev_langs: C++
helpviewer_keywords: C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: faea544c9e2328521c5d302bbb2af935c94201c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2689"></a>Erreur du compilateur C2689
'fonction' : une fonction friend ne peut pas être définie dans une classe locale  
  
 Vous pouvez déclarer mais pas définir une fonction friend dans une classe locale.  
  
 L’exemple suivant génère l’erreur C2689 :  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```