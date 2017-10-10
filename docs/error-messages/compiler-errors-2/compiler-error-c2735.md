---
title: Erreur du compilateur C2735 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2735
dev_langs:
- C++
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1008ef6178a4220bac718e08ba31a36d5db3242f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2735"></a>Erreur du compilateur C2735
' mot_clé ' n’est pas autorisé dans le spécificateur de type de paramètre formel  
  
 Le mot clé n’est pas valide dans ce contexte.  
  
 L’exemple suivant génère l’erreur C2735 :  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```
