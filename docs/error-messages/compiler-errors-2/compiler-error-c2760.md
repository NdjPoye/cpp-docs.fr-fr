---
title: Erreur du compilateur C2760 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2760
dev_langs: C++
helpviewer_keywords: C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 910c1748ab92b095f77da840b8727943a84d79d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2760"></a>Erreur du compilateur C2760
Erreur de syntaxe : attendu 'nom1' non 'nom2'  
  
 Un opérateur de cast est utilisé avec un opérateur non valide.  
  
 L’exemple suivant génère l’erreur C2760 :  
  
```  
// C2760.cpp  
class B {};  
class D : public B {};  
  
void f(B* pb) {  
    D* pd1 = static_cast<D*>(pb);  
    D* pd2 = static_cast<D*>=(pb);  // C2760  
    D* pd3 = static_cast<D*=(pb);   // C2760  
}  
```