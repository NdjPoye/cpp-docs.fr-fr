---
title: Erreur du compilateur C3354 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3354
dev_langs:
- C++
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e4fc95051f9a59db0fcb06fd4990637efda34516
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3354"></a>Erreur du compilateur C3354
'fonction' : la fonction utilisée pour créer un délégué ne peut pas avoir un type de retour 'type'  
  
 Les types suivants ne sont pas des types de retour valides pour un `delegate`:  
  
-   Pointeur vers fonction  
  
-   Pointeur vers membre  
  
-   Pointeur vers fonction membre  
  
-   Référence vers fonction  
  
-   Référence vers fonction membre  
  
 L’exemple suivant génère l’erreur C3354 :  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  

